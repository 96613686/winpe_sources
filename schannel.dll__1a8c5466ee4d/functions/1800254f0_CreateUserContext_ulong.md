# CreateUserContext(ulong)

- ea: `0x1800254f0`
- end: `0x180025615`
- name: `?CreateUserContext@@YAPEAUCSslUserContext@@K@Z`
- size: `293`
- prototype: `struct CSslUserContext *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180025ef0`

## callees

- `0x180021da8`
- `0x1800245f0`
- `0x1800254f0`
- `0x18005a160`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002554e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002554e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002552f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002552f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025592`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025592`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255cd`

## pseudocode

```c
struct CSslUserContext *__fastcall CreateUserContext(size_t Size)
{
  SIZE_T v1; // rbx
  size_t v2; // rdi
  CSslUserContext *v3; // rax
  CSslUserContext *v4; // rbx
  CSslUserContext *v5; // rbx
  signed int LastError; // eax
  bool v8; // zf
  void **v9; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-10h]

  v1 = (unsigned int)Size;
  if ( (unsigned int)Size < 0x1F8 )
    return 0;
  v9 = &CEvent::`vftable';
  hObject = CreateEventW(0, 1, 1, 0);
  if ( !hObject )
  {
    LastError = GetLastError();
    v8 = LastError == 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError == 0;
    }
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          128,
          &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
          (unsigned int)LastError);
      goto LABEL_8;
    }
  }
  v2 = v1;
  v3 = (CSslUserContext *)LocalAlloc(0x40u, v1);
  v4 = v3;
  if ( !v3 )
  {
LABEL_8:
    v9 = &CEvent::`vftable';
    if ( hObject )
      CloseHandle(hObject);
    return 0;
  }
  memset_0(v3, 0, v2);
  v5 = CSslUserContext::CSslUserContext(v4, (struct CEvent *)&v9);
  *((_DWORD *)v5 + 100) = -1;
  v9 = &CEvent::`vftable';
  if ( hObject )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x1800254f0  mov     [rsp+arg_0], rbx
0x1800254f5  mov     [rsp+arg_8], rsi
0x1800254fa  push    rdi
0x1800254fb  sub     rsp, 30h
0x1800254ff  mov     ebx, ecx
0x180025501  cmp     ecx, 1F8h
0x180025507  jb      loc_1800255D3
0x18002550d  mov     edx, 1; bManualReset
0x180025512  mov     [rsp+38h+hObject], 0
0x18002551b  lea     rsi, ??_7CEvent@@6B@; const CEvent::`vftable'
0x180025522  mov     r8d, edx; bInitialState
0x180025525  xor     r9d, r9d; lpName
0x180025528  mov     [rsp+38h+var_18], rsi
0x18002552d  xor     ecx, ecx; lpEventAttributes
0x18002552f  call    cs:__imp_CreateEventW
0x180025535  mov     [rsp+38h+hObject], rax
0x18002553a  test    rax, rax
0x18002553d  jz      loc_1800255D7
0x180025543  mov     rdx, rbx; uBytes
0x180025546  mov     ecx, 40h ; '@'; uFlags
0x18002554b  mov     rdi, rbx
0x18002554e  call    cs:__imp_LocalAlloc
0x180025554  mov     rbx, rax
0x180025557  test    rax, rax
0x18002555a  jz      short loc_1800255BE
0x18002555c  mov     r8, rdi; Size
0x18002555f  xor     edx, edx; Val
0x180025561  mov     rcx, rax; void *
0x180025564  call    memset_0
0x180025569  lea     rdx, [rsp+38h+var_18]; struct CEvent *
0x18002556e  mov     rcx, rbx; this
0x180025571  call    ??0CSslUserContext@@QEAA@AEAVCEvent@@@Z; CSslUserContext::CSslUserContext(CEvent &)
0x180025576  mov     rbx, rax
0x180025579  mov     dword ptr [rax+190h], 0FFFFFFFFh
0x180025583  mov     rcx, [rsp+38h+hObject]; hObject
0x180025588  mov     [rsp+38h+var_18], rsi
0x18002558d  test    rcx, rcx
0x180025590  jz      short loc_180025598
0x180025592  call    cs:__imp_CloseHandle
0x180025598  mov     rax, rbx
0x18002559b  mov     rbx, [rsp+38h+arg_0]
0x1800255a0  mov     rsi, [rsp+38h+arg_8]
0x1800255a5  add     rsp, 30h
0x1800255a9  pop     rdi
0x1800255aa  retn
0x1800255ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255b2  lea     rdx, WPP_GLOBAL_Control
0x1800255b9  cmp     rcx, rdx
0x1800255bc  jnz     short loc_1800255F5
0x1800255be  mov     rcx, [rsp+38h+hObject]; hObject
0x1800255c3  mov     [rsp+38h+var_18], rsi
0x1800255c8  test    rcx, rcx
0x1800255cb  jz      short loc_1800255D3
0x1800255cd  call    cs:__imp_CloseHandle
0x1800255d3  xor     eax, eax
0x1800255d5  jmp     short loc_18002559B
0x1800255d7  call    cs:__imp_GetLastError
0x1800255dd  test    eax, eax
0x1800255df  jg      short loc_1800255E9
0x1800255e1  jz      loc_180025543
0x1800255e7  jmp     short loc_1800255AB
0x1800255e9  movzx   eax, ax
0x1800255ec  or      eax, 80070000h
0x1800255f1  test    eax, eax
0x1800255f3  jmp     short loc_1800255E1
0x1800255f5  test    byte ptr [rcx+1Ch], 1
0x1800255f9  jz      short loc_1800255BE
0x1800255fb  mov     rcx, [rcx+10h]
0x1800255ff  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180025606  mov     edx, 80h
0x18002560b  mov     r9d, eax
0x18002560e  call    WPP_SF_d
0x180025613  jmp     short loc_1800255BE
```
