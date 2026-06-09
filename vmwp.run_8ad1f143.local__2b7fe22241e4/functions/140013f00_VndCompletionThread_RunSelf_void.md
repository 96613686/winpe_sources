# VndCompletionThread::RunSelf(void)

- ea: `0x140013f00`
- end: `0x1400140a4`
- name: `?RunSelf@VndCompletionThread@@MEAAIXZ`
- size: `420`
- prototype: `unsigned int __fastcall(VndCompletionThread *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140013f00`
- `0x1400140ac`
- `0x140132960`
- `0x14027e6c8`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014060`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001400d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001400d`
- `vid!VidHandleMessageAndGetNextMessage` at `0x14001404f`
- `vid!VidHandleMessageAndGetNextMessage` at `0x14001404f`
- `vid!VidMessageSlotHandleAndGetNext` at `0x140013f7a`
- `vid!VidMessageSlotHandleAndGetNext` at `0x140013f7a`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x140014024`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x140014024`

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
0x140013f00  push    rbx
0x140013f02  push    rsi
0x140013f03  push    rdi
0x140013f04  push    r14
0x140013f06  sub     rsp, 68h
0x140013f0a  mov     rax, cs:__security_cookie
0x140013f11  xor     rax, rsp
0x140013f14  mov     [rsp+88h+var_38], rax
0x140013f19  mov     rax, [rcx+78h]
0x140013f1d  mov     rbx, rcx
0x140013f20  mov     r8d, [rcx+90h]
0x140013f27  mov     r14, [rax+78h]
0x140013f2b  mov     [rsp+88h+var_50], 0
0x140013f34  mov     [rsp+88h+var_58], 0
0x140013f3d  test    r8d, r8d
0x140013f40  jns     loc_140013FD2
0x140013f46  mov     rax, [r14]
0x140013f49  xor     edi, edi
0x140013f4b  mov     rsi, [rax+28h]
0x140013f4f  jmp     short loc_140013FB1
0x140013f51  mov     eax, [rbx+90h]
0x140013f57  neg     edi
0x140013f59  mov     rcx, [rbx+98h]
0x140013f60  sbb     edx, edx
0x140013f62  and     edx, 2
0x140013f65  inc     edx
0x140013f67  test    eax, eax
0x140013f69  js      loc_140014035
0x140013f6f  mov     r9, rcx
0x140013f72  mov     r8d, edx
0x140013f75  mov     edx, eax
0x140013f77  mov     rcx, rsi
0x140013f7a  call    cs:__imp_VidMessageSlotHandleAndGetNext
0x140013f81  nop     dword ptr [rax+rax+00h]
0x140013f86  test    eax, eax
0x140013f88  jz      loc_140014060
0x140013f8e  mov     rax, [rbx+98h]
0x140013f95  mov     rdx, rsi; void *
0x140013f98  mov     r9, [rsp+88h+var_58]; struct _VID_MSG_RETURN_DATA *
0x140013f9d  mov     rcx, r14; this
0x140013fa0  mov     r8, [rsp+88h+var_50]; struct _VID_MSG_DATA *
0x140013fa5  mov     [rsp+88h+var_68], rax; unsigned int
0x140013faa  call    ?HandleVndCallback@VndCompletionHandler@@AEAAHPEAXPEAU_VID_MSG_DATA@@PEAU_VID_MSG_RETURN_DATA@@0@Z; VndCompletionHandler::HandleVndCallback(void *,_VID_MSG_DATA *,_VID_MSG_RETURN_DATA *,void *)
0x140013faf  mov     edi, eax
0x140013fb1  mov     al, [rbx+70h]
0x140013fb4  test    al, al
0x140013fb6  jnz     short loc_140013F51
0x140013fb8  xor     eax, eax
0x140013fba  mov     rcx, [rsp+88h+var_38]
0x140013fbf  xor     rcx, rsp; StackCookie
0x140013fc2  call    __security_check_cookie
0x140013fc7  add     rsp, 68h
0x140013fcb  pop     r14
0x140013fcd  pop     rdi
0x140013fce  pop     rsi
0x140013fcf  pop     rbx
0x140013fd0  retn
0x140013fd2  mov     rax, [rcx+80h]
0x140013fd9  lea     rdx, [rsp+88h+GroupAffinity]
0x140013fde  mov     [rsp+88h+var_50], rax
0x140013fe3  add     rax, 140h
0x140013fe9  mov     [rsp+88h+var_58], rax
0x140013fee  mov     rax, [r14]
0x140013ff1  mov     rcx, [rax+38h]
0x140013ff5  mov     rax, [rcx]
0x140013ff8  mov     rax, [rax+40h]
0x140013ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014001  cmp     [rsp+88h+GroupAffinity.Mask], 0
0x140014007  jz      loc_140013F46
0x14001400d  call    cs:__imp_GetCurrentThread
0x140014014  nop     dword ptr [rax+rax+00h]
0x140014019  xor     r8d, r8d; PreviousGroupAffinity
0x14001401c  lea     rdx, [rsp+88h+GroupAffinity]; GroupAffinity
0x140014021  mov     rcx, rax; hThread
0x140014024  call    cs:__imp_SetThreadGroupAffinity
0x14001402b  nop     dword ptr [rax+rax+00h]
0x140014030  jmp     loc_140013F46
0x140014035  mov     [rsp+88h+var_60], rcx
0x14001403a  lea     r9, [rsp+88h+var_50]
0x14001403f  mov     rcx, rsi
0x140014042  mov     dword ptr [rsp+88h+var_68], 0FFFFFFFFh
0x14001404a  lea     r8, [rsp+88h+var_58]
0x14001404f  call    cs:__imp_VidHandleMessageAndGetNextMessage
0x140014056  nop     dword ptr [rax+rax+00h]
0x14001405b  jmp     loc_140013F86
0x140014060  call    cs:__imp_GetLastError
0x140014067  nop     dword ptr [rax+rax+00h]
0x14001406c  mov     cl, [rbx+70h]
0x14001406f  xor     edi, edi
0x140014071  test    cl, cl
0x140014073  jz      loc_140013FB1
0x140014079  cmp     eax, 102h
0x14001407e  jz      loc_140013FB1
0x140014084  cmp     eax, 3E3h
0x140014089  jz      loc_140013FB1
0x14001408f  mov     rcx, [rsp+88h]; this
0x140014097  mov     r9d, eax; char *
0x14001409a  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x14001409f  jmp     loc_140013FB1
```
