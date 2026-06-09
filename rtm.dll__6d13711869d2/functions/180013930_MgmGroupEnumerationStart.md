# MgmGroupEnumerationStart

- ea: `0x180013930`
- end: `0x180013aee`
- name: `MgmGroupEnumerationStart`
- size: `446`
- prototype: `DWORD __stdcall(HANDLE hProtocol, MGM_ENUM_TYPES metEnumType, HANDLE *phEnumHandle)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180013930`
- `0x180014bfc`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x18001b588`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800139d8`
- `KERNEL32!HeapAlloc` at `0x1800139d8`
- `rtutils!RouterLogEventA` at `0x180013a52`
- `rtutils!RouterLogEventA` at `0x180013a52`

## pseudocode

```c
DWORD __stdcall MgmGroupEnumerationStart(HANDLE hProtocol, MGM_ENUM_TYPES metEnumType, HANDLE *phEnumHandle)
{
  DWORD v6; // ebx
  unsigned __int64 v7; // rax
  int v8; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-814h] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"ENTERED MgmGroupEnumerationStart");
  AcquireReadLock(&qword_18002B9B8);
  v6 = VerifyProtocolHandle((unsigned __int64)hProtocol ^ 0x474D6300);
  if ( !v6 )
  {
    v7 = (unsigned __int64)HeapAlloc(hHeap, 0, 0x18u);
    if ( v7 )
    {
      *(_OWORD *)v7 = 0;
      *(_QWORD *)(v7 + 16) = 0;
      *(_DWORD *)(v7 + 20) = 1163094375;
      *phEnumHandle = (HANDLE)(v7 ^ 0x474D6500);
    }
    else
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"Failed to allocate group enumerator of size : %d", v6 + 24);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v8);
      }
      v6 = 8;
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
    }
  }
  ReleaseReadLock((__int64)&qword_18002B9B8);
  if ( qword_18002B8A8 )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"LEAVING MgmGroupEnumerationStart\n", v6);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v8);
  }
  LeaveMgmWorker();
  return v6;
}

```

## disassembly

```asm
0x180013930  mov     [rsp+arg_8], rbx
0x180013935  push    rdi
0x180013936  sub     rsp, 840h
0x18001393d  mov     rax, cs:__security_cookie
0x180013944  xor     rax, rsp
0x180013947  mov     [rsp+848h+var_18], rax
0x18001394f  mov     rdi, r8
0x180013952  mov     rbx, rcx
0x180013955  xor     eax, eax
0x180013957  lea     rcx, [rsp+848h+var_814]; void *
0x18001395c  mov     r8d, 7FCh; Size
0x180013962  mov     [rsp+848h+var_818], eax
0x180013966  xor     edx, edx; Val
0x180013968  call    memset_0
0x18001396d  call    EnterMgmAPI
0x180013972  test    eax, eax
0x180013974  jnz     short loc_180013980
0x180013976  mov     eax, 3EBh
0x18001397b  jmp     loc_180013ACD
0x180013980  mov     rdx, cs:qword_18002B8A8
0x180013987  test    rdx, rdx
0x18001398a  jz      short loc_1800139A6
0x18001398c  mov     rcx, cs:gMgmEtwContext
0x180013993  lea     r8, aEnteredMgmgrou; "ENTERED MgmGroupEnumerationStart"
0x18001399a  mov     rax, cs:gMgmTemplateFunc
0x1800139a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a6  lea     rcx, qword_18002B9B8
0x1800139ad  call    AcquireReadLock
0x1800139b2  xor     rbx, 474D6300h
0x1800139b9  mov     rcx, rbx
0x1800139bc  call    VerifyProtocolHandle
0x1800139c1  mov     ebx, eax
0x1800139c3  test    eax, eax
0x1800139c5  jnz     loc_180013A76
0x1800139cb  mov     rcx, cs:hHeap; hHeap
0x1800139d2  lea     r8d, [rax+18h]; dwBytes
0x1800139d6  xor     edx, edx; dwFlags
0x1800139d8  call    cs:__imp_HeapAlloc
0x1800139de  test    rax, rax
0x1800139e1  jnz     short loc_180013A5A
0x1800139e3  cmp     cs:qword_18002B8A8, rax
0x1800139ea  jz      short loc_180013A25
0x1800139ec  lea     r8d, [rbx+18h]
0x1800139f0  mov     word ptr [rsp+848h+var_818], ax
0x1800139f5  lea     rdx, aFailedToAlloca_2; "Failed to allocate group enumerator of "...
0x1800139fc  lea     rcx, [rsp+848h+var_818]
0x180013a01  call    FormatRRASErrorString
0x180013a06  mov     rdx, cs:qword_18002B8A8
0x180013a0d  lea     r8, [rsp+848h+var_818]
0x180013a12  mov     rcx, cs:gMgmEtwContext
0x180013a19  mov     rax, cs:gMgmTemplateFunc
0x180013a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a25  mov     ebx, 8
0x180013a2a  lea     edx, [rbx-7]; dwEventType
0x180013a2d  cmp     cs:dword_18002BA54, edx
0x180013a33  jb      short loc_180013A76
0x180013a35  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180013a3c  xor     r9d, r9d; dwSubStringCount
0x180013a3f  mov     [rsp+848h+dwErrorCode], ebx; dwErrorCode
0x180013a43  mov     r8d, 0C353h; dwMessageId
0x180013a49  mov     [rsp+848h+plpszSubStringArray], 0; plpszSubStringArray
0x180013a52  call    cs:__imp_RouterLogEventA
0x180013a58  jmp     short loc_180013A76
0x180013a5a  xor     edx, edx
0x180013a5c  xorps   xmm0, xmm0
0x180013a5f  movups  xmmword ptr [rax], xmm0
0x180013a62  mov     [rax+10h], rdx
0x180013a66  mov     dword ptr [rax+14h], 45536967h
0x180013a6d  xor     rax, 474D6500h
0x180013a73  mov     [rdi], rax
0x180013a76  lea     rcx, qword_18002B9B8
0x180013a7d  call    ReleaseReadLock
0x180013a82  cmp     cs:qword_18002B8A8, 0
0x180013a8a  jz      short loc_180013AC6
0x180013a8c  xor     eax, eax
0x180013a8e  lea     rdx, aLeavingMgmgrou_0; "LEAVING MgmGroupEnumerationStart\n"
0x180013a95  mov     r8d, ebx
0x180013a98  mov     word ptr [rsp+848h+var_818], ax
0x180013a9d  lea     rcx, [rsp+848h+var_818]
0x180013aa2  call    FormatRRASErrorString
0x180013aa7  mov     rdx, cs:qword_18002B8A8
0x180013aae  lea     r8, [rsp+848h+var_818]
0x180013ab3  mov     rcx, cs:gMgmEtwContext
0x180013aba  mov     rax, cs:gMgmTemplateFunc
0x180013ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ac6  call    LeaveMgmWorker
0x180013acb  mov     eax, ebx
0x180013acd  mov     rcx, [rsp+848h+var_18]
0x180013ad5  xor     rcx, rsp; StackCookie
0x180013ad8  call    __security_check_cookie
0x180013add  mov     rbx, [rsp+848h+arg_8]
0x180013ae5  add     rsp, 840h
0x180013aec  pop     rdi
0x180013aed  retn
```
