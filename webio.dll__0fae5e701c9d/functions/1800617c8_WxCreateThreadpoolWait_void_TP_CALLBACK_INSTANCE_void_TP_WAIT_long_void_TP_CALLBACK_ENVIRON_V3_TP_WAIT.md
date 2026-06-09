# WxCreateThreadpoolWait(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_WAIT * *)

- ea: `0x1800617c8`
- end: `0x1800618be`
- name: `?WxCreateThreadpoolWait@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z`
- size: `246`
- prototype: `__int64 __fastcall(void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int), void *, struct _TP_CALLBACK_ENVIRON_V3 *, struct _TP_WAIT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180061630`

## callees

- `0x1800617c8`
- `0x1800619fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006182d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006182d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180061814`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180061814`

## pseudocode

```c
__int64 __fastcall WxCreateThreadpoolWait(
        void (*a1)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int),
        void *a2,
        struct _TP_CALLBACK_ENVIRON_V3 *a3,
        struct _TP_WAIT **a4)
{
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int LastError; // eax
  signed int v7; // ebx

  if ( a4 )
  {
    *a4 = 0;
    if ( *(_BYTE *)(qword_1800AE6B0 + 72) )
    {
      v7 = -2147024809;
    }
    else
    {
      ThreadpoolWait = CreateThreadpoolWait(
                         FailFastThreadpoolWaitCallback<&void SafeTerminateDll(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)>,
                         a2,
                         0);
      if ( ThreadpoolWait )
      {
        v7 = 0;
        *a4 = ThreadpoolWait;
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2147418113;
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  WxCloseThreadpoolWait(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800617c8  mov     rax, rsp
0x1800617cb  mov     [rax+8], rbx
0x1800617cf  mov     [rax+10h], rsi
0x1800617d3  push    rdi
0x1800617d4  sub     rsp, 30h
0x1800617d8  mov     rsi, r9
0x1800617db  mov     dword ptr [rax+1Ch], 0
0x1800617e2  xor     edi, edi
0x1800617e4  mov     [rax-18h], rdi
0x1800617e8  test    r9, r9
0x1800617eb  jz      short loc_1800617F0
0x1800617ed  mov     [r9], rdi
0x1800617f0  test    rsi, rsi
0x1800617f3  jz      loc_1800618AF
0x1800617f9  mov     rax, cs:qword_1800AE6B0
0x180061800  cmp     [rax+48h], dil
0x180061804  jnz     loc_1800618A0
0x18006180a  xor     r8d, r8d; pcbe
0x18006180d  lea     rcx, ??$FailFastThreadpoolWaitCallback@$1?SafeTerminateDll@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180061814  call    cs:__imp_CreateThreadpoolWait
0x18006181b  nop     dword ptr [rax+rax+00h]
0x180061820  mov     rdi, rax
0x180061823  mov     [rsp+38h+var_18], rax
0x180061828  test    rax, rax
0x18006182b  jnz     short loc_180061864
0x18006182d  call    cs:__imp_GetLastError
0x180061834  nop     dword ptr [rax+rax+00h]
0x180061839  mov     ebx, eax
0x18006183b  test    eax, eax
0x18006183d  jle     short loc_180061848
0x18006183f  movzx   ebx, ax
0x180061842  or      ebx, 80070000h
0x180061848  mov     [rsp+38h+arg_10], ebx
0x18006184c  mov     eax, 8000FFFFh
0x180061851  test    ebx, ebx
0x180061853  cmovns  ebx, eax
0x180061856  mov     [rsp+38h+arg_10], ebx
0x18006185a  mov     [rsp+38h+arg_14], 10Ch
0x180061862  jmp     short loc_180061885
0x180061864  xor     ebx, ebx
0x180061866  mov     [rsp+38h+arg_10], ebx
0x18006186a  jmp     short loc_180061880
0x18006186c  mov     ebx, 80070057h
0x180061871  mov     [rsp+38h+arg_14], 110h
0x180061879  mov     rdi, [rsp+38h+var_18]
0x18006187e  jmp     short loc_180061885
0x180061880  mov     [rsi], rax
0x180061883  xor     edi, edi
0x180061885  mov     rcx, rdi; struct _TP_WAIT *
0x180061888  call    ?WxCloseThreadpoolWait@@YAXPEAU_TP_WAIT@@@Z; WxCloseThreadpoolWait(_TP_WAIT *)
0x18006188d  mov     eax, ebx
0x18006188f  mov     rbx, [rsp+38h+arg_0]
0x180061894  mov     rsi, [rsp+38h+arg_8]
0x180061899  add     rsp, 30h
0x18006189d  pop     rdi
0x18006189e  retn
0x1800618a0  mov     ebx, 80070057h
0x1800618a5  mov     [rsp+38h+arg_14], 107h
0x1800618ad  jmp     short loc_180061885
0x1800618af  mov     ebx, 80070057h
0x1800618b4  mov     [rsp+38h+arg_14], 105h
0x1800618bc  jmp     short loc_180061885
0x180091a81  push    rbp
0x180091a83  sub     rsp, 20h
0x180091a87  mov     rbp, rdx
0x180091a8a  mov     rax, [rcx]
0x180091a8d  xor     ecx, ecx
0x180091a8f  cmp     dword ptr [rax], 0C000000Dh
0x180091a95  setz    cl
0x180091a98  mov     eax, ecx
0x180091a9a  add     rsp, 20h
0x180091a9e  pop     rbp
0x180091a9f  retn
```
