# MgmDeRegisterMProtocol

- ea: `0x180012620`
- end: `0x1800127ef`
- name: `MgmDeRegisterMProtocol`
- size: `463`
- prototype: `DWORD __stdcall(HANDLE hProtocol)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180012620`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015178`
- `0x18001b588`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800127d5`
- `KERNEL32!HeapFree` at `0x1800127d5`
- `rtutils!RouterLogEventA` at `0x180012732`
- `rtutils!RouterLogEventA` at `0x180012732`

## string_xrefs

- `0x180012680`: `ENTERED MgmDeRegisterMProtocol`
- `0x1800126d8`: `%x interfaces present for this protocol`
- `0x180012750`: `LEAVING MgmDeRegisterMProtocol %x\n`

## pseudocode

```c
DWORD __stdcall MgmDeRegisterMProtocol(HANDLE hProtocol)
{
  _QWORD *v3; // rdi
  DWORD v4; // ebx
  __int64 v5; // rax
  _QWORD *v6; // rcx
  int v7; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v8[2044]; // [rsp+34h] [rbp-814h] BYREF

  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"ENTERED MgmDeRegisterMProtocol");
  AcquireWriteLock(&qword_18002B9B8);
  v3 = (_QWORD *)((unsigned __int64)hProtocol ^ 0x474D6300);
  v4 = VerifyProtocolHandle(v3);
  if ( !v4 )
  {
    if ( *((_DWORD *)v3 + 6) )
    {
      v4 = 1003;
      if ( qword_18002B8A8 )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString(&v7, L"%x interfaces present for this protocol", 1003);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v7);
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC35Du, 0, 0, 0x3EBu);
    }
    else
    {
      v5 = *v3;
      if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v6 = (_QWORD *)v3[1], (_QWORD *)*v6 != v3) )
        __fastfail(3u);
      *v6 = v5;
      *(_QWORD *)(v5 + 8) = v6;
      HeapFree(hHeap, 0, v3);
      --dword_18002B9A0;
      v4 = 0;
    }
  }
  ReleaseWriteLock(&qword_18002B9B8);
  if ( qword_18002B8A8 )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString(&v7, L"LEAVING MgmDeRegisterMProtocol %x\n", v4);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v7);
  }
  LeaveMgmWorker();
  return v4;
}

```

## disassembly

```asm
0x180012620  mov     [rsp+arg_8], rbx
0x180012625  push    rdi
0x180012626  sub     rsp, 840h
0x18001262d  mov     rax, cs:__security_cookie
0x180012634  xor     rax, rsp
0x180012637  mov     [rsp+848h+var_18], rax
0x18001263f  mov     rdi, rcx
0x180012642  xor     eax, eax
0x180012644  lea     rcx, [rsp+848h+var_814]; void *
0x180012649  mov     [rsp+848h+var_818], eax
0x18001264d  xor     edx, edx; Val
0x18001264f  mov     r8d, 7FCh; Size
0x180012655  call    memset_0
0x18001265a  call    EnterMgmAPI
0x18001265f  test    eax, eax
0x180012661  jnz     short loc_18001266D
0x180012663  mov     eax, 3EBh
0x180012668  jmp     loc_18001278F
0x18001266d  mov     rdx, cs:qword_18002B8A8
0x180012674  test    rdx, rdx
0x180012677  jz      short loc_180012693
0x180012679  mov     rcx, cs:gMgmEtwContext
0x180012680  lea     r8, aEnteredMgmdere; "ENTERED MgmDeRegisterMProtocol"
0x180012687  mov     rax, cs:gMgmTemplateFunc
0x18001268e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012693  lea     rcx, qword_18002B9B8
0x18001269a  call    AcquireWriteLock
0x18001269f  xor     rdi, 474D6300h
0x1800126a6  mov     rcx, rdi
0x1800126a9  call    VerifyProtocolHandle
0x1800126ae  mov     ebx, eax
0x1800126b0  test    eax, eax
0x1800126b2  jnz     loc_180012738
0x1800126b8  cmp     [rdi+18h], eax
0x1800126bb  jz      loc_1800127B0
0x1800126c1  cmp     cs:qword_18002B8A8, 0
0x1800126c9  mov     ebx, 3EBh
0x1800126ce  jz      short loc_180012708
0x1800126d0  mov     r8d, ebx
0x1800126d3  mov     word ptr [rsp+848h+var_818], ax
0x1800126d8  lea     rdx, aXInterfacesPre; "%x interfaces present for this protocol"
0x1800126df  lea     rcx, [rsp+848h+var_818]
0x1800126e4  call    FormatRRASErrorString
0x1800126e9  mov     rdx, cs:qword_18002B8A8
0x1800126f0  lea     r8, [rsp+848h+var_818]
0x1800126f5  mov     rcx, cs:gMgmEtwContext
0x1800126fc  mov     rax, cs:gMgmTemplateFunc
0x180012703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012708  mov     edx, 1; dwEventType
0x18001270d  cmp     cs:dword_18002BA54, edx
0x180012713  jb      short loc_180012738
0x180012715  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001271c  xor     r9d, r9d; dwSubStringCount
0x18001271f  mov     [rsp+848h+dwErrorCode], ebx; dwErrorCode
0x180012723  mov     r8d, 0C35Dh; dwMessageId
0x180012729  mov     [rsp+848h+plpszSubStringArray], 0; plpszSubStringArray
0x180012732  call    cs:__imp_RouterLogEventA
0x180012738  lea     rcx, qword_18002B9B8
0x18001273f  call    ReleaseWriteLock
0x180012744  cmp     cs:qword_18002B8A8, 0
0x18001274c  jz      short loc_180012788
0x18001274e  xor     eax, eax
0x180012750  lea     rdx, aLeavingMgmdere; "LEAVING MgmDeRegisterMProtocol %x\n"
0x180012757  mov     r8d, ebx
0x18001275a  mov     word ptr [rsp+848h+var_818], ax
0x18001275f  lea     rcx, [rsp+848h+var_818]
0x180012764  call    FormatRRASErrorString
0x180012769  mov     rdx, cs:qword_18002B8A8
0x180012770  lea     r8, [rsp+848h+var_818]
0x180012775  mov     rcx, cs:gMgmEtwContext
0x18001277c  mov     rax, cs:gMgmTemplateFunc
0x180012783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012788  call    LeaveMgmWorker
0x18001278d  mov     eax, ebx
0x18001278f  mov     rcx, [rsp+848h+var_18]
0x180012797  xor     rcx, rsp; StackCookie
0x18001279a  call    __security_check_cookie
0x18001279f  mov     rbx, [rsp+848h+arg_8]
0x1800127a7  add     rsp, 840h
0x1800127ae  pop     rdi
0x1800127af  retn
0x1800127b0  mov     rax, [rdi]
0x1800127b3  cmp     [rax+8], rdi
0x1800127b7  jnz     short loc_1800127E8
0x1800127b9  mov     rcx, [rdi+8]
0x1800127bd  cmp     [rcx], rdi
0x1800127c0  jnz     short loc_1800127E8
0x1800127c2  mov     [rcx], rax
0x1800127c5  mov     r8, rdi; lpMem
0x1800127c8  mov     [rax+8], rcx
0x1800127cc  xor     edx, edx; dwFlags
0x1800127ce  mov     rcx, cs:hHeap; hHeap
0x1800127d5  call    cs:__imp_HeapFree
0x1800127db  dec     cs:dword_18002B9A0
0x1800127e1  xor     ebx, ebx
0x1800127e3  jmp     loc_180012738
0x1800127e8  mov     ecx, 3
0x1800127ed  int     29h; Win8: RtlFailFast(ecx)
```
