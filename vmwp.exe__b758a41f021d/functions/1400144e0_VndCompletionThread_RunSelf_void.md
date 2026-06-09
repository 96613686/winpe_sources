# VndCompletionThread::RunSelf(void)

- ea: `0x1400144e0`
- end: `0x140014684`
- name: `?RunSelf@VndCompletionThread@@MEAAIXZ`
- size: `420`
- prototype: `unsigned int __fastcall(VndCompletionThread *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400144e0`
- `0x14001468c`
- `0x14011ea40`
- `0x1402849d8`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014640`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400145ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400145ed`
- `vid!VidHandleMessageAndGetNextMessage` at `0x14001462f`
- `vid!VidHandleMessageAndGetNextMessage` at `0x14001462f`
- `vid!VidMessageSlotHandleAndGetNext` at `0x14001455a`
- `vid!VidMessageSlotHandleAndGetNext` at `0x14001455a`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x140014604`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x140014604`

## pseudocode

```c
__int64 __fastcall VndCompletionThread::RunSelf(VndCompletionThread *this)
{
  int v2; // r8d
  VndCompletionHandler *v3; // r14
  int v4; // edi
  void *v5; // rsi
  int v6; // eax
  __int64 v7; // rdx
  int NextMessage; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // [rsp+20h] [rbp-68h]
  struct _VID_MSG_RETURN_DATA *v15; // [rsp+30h] [rbp-58h] BYREF
  struct _VID_MSG_DATA *v16; // [rsp+38h] [rbp-50h] BYREF
  GROUP_AFFINITY GroupAffinity; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = *((_DWORD *)this + 36);
  v3 = *(VndCompletionHandler **)(*((_QWORD *)this + 15) + 120LL);
  v16 = 0;
  v15 = 0;
  if ( v2 >= 0 )
  {
    v16 = (struct _VID_MSG_DATA *)*((_QWORD *)this + 16);
    v15 = (struct _VID_MSG_DATA *)((char *)v16 + 320);
    (*(void (__fastcall **)(_QWORD, GROUP_AFFINITY *))(**(_QWORD **)(*(_QWORD *)v3 + 56LL) + 64LL))(
      *(_QWORD *)(*(_QWORD *)v3 + 56LL),
      &GroupAffinity);
    if ( GroupAffinity.Mask )
    {
      CurrentThread = GetCurrentThread();
      SetThreadGroupAffinity(CurrentThread, &GroupAffinity, 0);
    }
  }
  v4 = 0;
  v5 = *(void **)(*(_QWORD *)v3 + 40LL);
  while ( *((_BYTE *)this + 112) )
  {
    v6 = *((_DWORD *)this + 36);
    v7 = v4 != 0 ? 3 : 1;
    if ( v6 < 0 )
    {
      v14 = -1;
      NextMessage = VidHandleMessageAndGetNextMessage(v5, v7, &v15, &v16);
    }
    else
    {
      NextMessage = VidMessageSlotHandleAndGetNext(v5, (unsigned int)v6, (unsigned int)v7, *((_QWORD *)this + 19));
    }
    if ( NextMessage )
    {
      v4 = VndCompletionHandler::HandleVndCallback(v3, v5, v16, v15, *((void **)this + 19));
    }
    else
    {
      LastError = GetLastError();
      v4 = 0;
      if ( *((_BYTE *)this + 112) && LastError != 258 && LastError != 995 )
        wil::details::in1diag3::Log_Win32(retaddr, v12, v13, (const char *)LastError, v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400144e0  push    rbx
0x1400144e2  push    rsi
0x1400144e3  push    rdi
0x1400144e4  push    r14
0x1400144e6  sub     rsp, 68h
0x1400144ea  mov     rax, cs:__security_cookie
0x1400144f1  xor     rax, rsp
0x1400144f4  mov     [rsp+88h+var_38], rax
0x1400144f9  mov     rax, [rcx+78h]
0x1400144fd  mov     rbx, rcx
0x140014500  mov     r8d, [rcx+90h]
0x140014507  mov     r14, [rax+78h]
0x14001450b  mov     [rsp+88h+var_50], 0
0x140014514  mov     [rsp+88h+var_58], 0
0x14001451d  test    r8d, r8d
0x140014520  jns     loc_1400145B2
0x140014526  mov     rax, [r14]
0x140014529  xor     edi, edi
0x14001452b  mov     rsi, [rax+28h]
0x14001452f  jmp     short loc_140014591
0x140014531  mov     eax, [rbx+90h]
0x140014537  neg     edi
0x140014539  mov     rcx, [rbx+98h]
0x140014540  sbb     edx, edx
0x140014542  and     edx, 2
0x140014545  inc     edx
0x140014547  test    eax, eax
0x140014549  js      loc_140014615
0x14001454f  mov     r9, rcx
0x140014552  mov     r8d, edx
0x140014555  mov     edx, eax
0x140014557  mov     rcx, rsi
0x14001455a  call    cs:__imp_VidMessageSlotHandleAndGetNext
0x140014561  nop     dword ptr [rax+rax+00h]
0x140014566  test    eax, eax
0x140014568  jz      loc_140014640
0x14001456e  mov     rax, [rbx+98h]
0x140014575  mov     rdx, rsi; void *
0x140014578  mov     r9, [rsp+88h+var_58]; struct _VID_MSG_RETURN_DATA *
0x14001457d  mov     rcx, r14; this
0x140014580  mov     r8, [rsp+88h+var_50]; struct _VID_MSG_DATA *
0x140014585  mov     [rsp+88h+var_68], rax; unsigned int
0x14001458a  call    ?HandleVndCallback@VndCompletionHandler@@AEAAHPEAXPEAU_VID_MSG_DATA@@PEAU_VID_MSG_RETURN_DATA@@0@Z; VndCompletionHandler::HandleVndCallback(void *,_VID_MSG_DATA *,_VID_MSG_RETURN_DATA *,void *)
0x14001458f  mov     edi, eax
0x140014591  mov     al, [rbx+70h]
0x140014594  test    al, al
0x140014596  jnz     short loc_140014531
0x140014598  xor     eax, eax
0x14001459a  mov     rcx, [rsp+88h+var_38]
0x14001459f  xor     rcx, rsp; StackCookie
0x1400145a2  call    __security_check_cookie
0x1400145a7  add     rsp, 68h
0x1400145ab  pop     r14
0x1400145ad  pop     rdi
0x1400145ae  pop     rsi
0x1400145af  pop     rbx
0x1400145b0  retn
0x1400145b2  mov     rax, [rcx+80h]
0x1400145b9  lea     rdx, [rsp+88h+GroupAffinity]
0x1400145be  mov     [rsp+88h+var_50], rax
0x1400145c3  add     rax, 140h
0x1400145c9  mov     [rsp+88h+var_58], rax
0x1400145ce  mov     rax, [r14]
0x1400145d1  mov     rcx, [rax+38h]
0x1400145d5  mov     rax, [rcx]
0x1400145d8  mov     rax, [rax+40h]
0x1400145dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400145e1  cmp     [rsp+88h+GroupAffinity.Mask], 0
0x1400145e7  jz      loc_140014526
0x1400145ed  call    cs:__imp_GetCurrentThread
0x1400145f4  nop     dword ptr [rax+rax+00h]
0x1400145f9  xor     r8d, r8d; PreviousGroupAffinity
0x1400145fc  lea     rdx, [rsp+88h+GroupAffinity]; GroupAffinity
0x140014601  mov     rcx, rax; hThread
0x140014604  call    cs:__imp_SetThreadGroupAffinity
0x14001460b  nop     dword ptr [rax+rax+00h]
0x140014610  jmp     loc_140014526
0x140014615  mov     [rsp+88h+var_60], rcx
0x14001461a  lea     r9, [rsp+88h+var_50]
0x14001461f  mov     rcx, rsi
0x140014622  mov     dword ptr [rsp+88h+var_68], 0FFFFFFFFh
0x14001462a  lea     r8, [rsp+88h+var_58]
0x14001462f  call    cs:__imp_VidHandleMessageAndGetNextMessage
0x140014636  nop     dword ptr [rax+rax+00h]
0x14001463b  jmp     loc_140014566
0x140014640  call    cs:__imp_GetLastError
0x140014647  nop     dword ptr [rax+rax+00h]
0x14001464c  mov     cl, [rbx+70h]
0x14001464f  xor     edi, edi
0x140014651  test    cl, cl
0x140014653  jz      loc_140014591
0x140014659  cmp     eax, 102h
0x14001465e  jz      loc_140014591
0x140014664  cmp     eax, 3E3h
0x140014669  jz      loc_140014591
0x14001466f  mov     rcx, [rsp+88h]; this
0x140014677  mov     r9d, eax; char *
0x14001467a  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x14001467f  jmp     loc_140014591
```
