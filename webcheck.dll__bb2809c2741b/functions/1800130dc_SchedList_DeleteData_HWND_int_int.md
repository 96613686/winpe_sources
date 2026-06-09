# SchedList_DeleteData(HWND__ *,int,int)

- ea: `0x1800130dc`
- end: `0x18001318d`
- name: `?SchedList_DeleteData@@YAXPEAUHWND__@@HH@Z`
- size: `177`
- prototype: `void __fastcall(HWND, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001419c`
- `0x1800143b0`

## callees

- `0x1800130dc`
- `0x180013194`
- `0x180013214`
- `0x18001ba40`
- `0x18002924e`

## import_xrefs

- `USER32!SendMessageW` at `0x18001314c`
- `USER32!SendMessageW` at `0x180013172`
- `USER32!SendMessageW` at `0x18001314c`
- `USER32!SendMessageW` at `0x180013172`

## pseudocode

```c
void __fastcall SchedList_DeleteData(HWND a1, int a2, int a3)
{
  int Index; // eax
  struct SCHED_LIST_DATA *Data; // rax
  struct SCHED_LIST_DATA *v8; // rbx
  int lParam; // [rsp+20h] [rbp-68h] BYREF
  int lParam_4; // [rsp+24h] [rbp-64h]
  __int64 v11; // [rsp+48h] [rbp-40h]

  memset_0(&lParam, 0, 0x58u);
  Index = SchedList_GetIndex(a1, a2);
  lParam_4 = Index;
  if ( Index != -1 )
  {
    Data = SchedList_GetData(a1, Index);
    lParam = 4;
    v8 = Data;
    v11 = 0;
    if ( Data && (unsigned int)SendMessageW(a1, 0x104Cu, 0, (LPARAM)&lParam) )
      operator delete(v8);
    if ( a3 )
      SendMessageW(a1, 0x1008u, lParam_4, 0);
  }
}

```

## disassembly

```asm
0x1800130dc  mov     [rsp+arg_0], rbx
0x1800130e1  mov     [rsp+arg_8], rsi
0x1800130e6  push    rdi
0x1800130e7  sub     rsp, 80h
0x1800130ee  mov     ebx, edx
0x1800130f0  mov     esi, r8d
0x1800130f3  xor     edx, edx; Val
0x1800130f5  mov     rdi, rcx
0x1800130f8  lea     rcx, [rsp+88h+lParam]; void *
0x1800130fd  lea     r8d, [rdx+58h]; Size
0x180013101  call    memset_0
0x180013106  mov     edx, ebx; int
0x180013108  mov     rcx, rdi; HWND
0x18001310b  call    ?SchedList_GetIndex@@YAHPEAUHWND__@@H@Z; SchedList_GetIndex(HWND__ *,int)
0x180013110  mov     dword ptr [rsp+88h+lParam+4], eax
0x180013114  cmp     eax, 0FFFFFFFFh
0x180013117  jz      short loc_180013178
0x180013119  mov     edx, eax; int
0x18001311b  mov     rcx, rdi; HWND
0x18001311e  call    ?SchedList_GetData@@YAPEAUSCHED_LIST_DATA@@PEAUHWND__@@H@Z; SchedList_GetData(HWND__ *,int)
0x180013123  mov     dword ptr [rsp+88h+lParam], 4
0x18001312b  mov     rbx, rax
0x18001312e  mov     [rsp+88h+var_40], 0
0x180013137  test    rax, rax
0x18001313a  jz      short loc_18001315E
0x18001313c  lea     r9, [rsp+88h+lParam]; lParam
0x180013141  xor     r8d, r8d; wParam
0x180013144  mov     edx, 104Ch; Msg
0x180013149  mov     rcx, rdi; hWnd
0x18001314c  call    cs:__imp_SendMessageW
0x180013152  test    eax, eax
0x180013154  jz      short loc_18001315E
0x180013156  mov     rcx, rbx; lpMem
0x180013159  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001315e  test    esi, esi
0x180013160  jz      short loc_180013178
0x180013162  movsxd  r8, dword ptr [rsp+88h+lParam+4]; wParam
0x180013167  xor     r9d, r9d; lParam
0x18001316a  mov     edx, 1008h; Msg
0x18001316f  mov     rcx, rdi; hWnd
0x180013172  call    cs:__imp_SendMessageW
0x180013178  lea     r11, [rsp+88h+var_8]
0x180013180  mov     rbx, [r11+10h]
0x180013184  mov     rsi, [r11+18h]
0x180013188  mov     rsp, r11
0x18001318b  pop     rdi
0x18001318c  retn
```
