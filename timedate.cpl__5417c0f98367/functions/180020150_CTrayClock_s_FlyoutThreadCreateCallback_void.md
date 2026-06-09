# CTrayClock::s_FlyoutThreadCreateCallback(void *)

- ea: `0x180020150`
- end: `0x1800201bd`
- name: `?s_FlyoutThreadCreateCallback@CTrayClock@@CAKPEAX@Z`
- size: `109`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180016e28`
- `0x18001f928`
- `0x18001fd0c`
- `0x180020150`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002016e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002016e`
- `USER32!PostThreadMessageW` at `0x1800201a1`
- `USER32!PostThreadMessageW` at `0x1800201a1`

## pseudocode

```c
__int64 __fastcall CTrayClock::s_FlyoutThreadCreateCallback(CTrayClock *Parameter)
{
  CTrayClock *v2; // rcx
  int v3; // eax

  if ( Parameter )
  {
    (*(void (__fastcall **)(CTrayClock *))(*(_QWORD *)Parameter + 8LL))(Parameter);
    *((_DWORD *)Parameter + 17) = GetCurrentThreadId();
    v3 = CTrayClock::_InitializeFlyout(v2);
    *((_DWORD *)Parameter + 19) = v3;
    if ( v3 >= 0 )
      *((_DWORD *)Parameter + 18) = CTrayClock::_OpenUp(Parameter);
    if ( *((int *)Parameter + 18) < 0 && !PostThreadMessageW(*((_DWORD *)Parameter + 17), 0x12u, 0, 0) )
      ResultFromKnownLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x180020150  mov     [rsp+arg_0], rbx
0x180020155  push    rdi
0x180020156  sub     rsp, 20h
0x18002015a  mov     rbx, rcx
0x18002015d  test    rcx, rcx
0x180020160  jz      short loc_1800201B0
0x180020162  mov     rax, [rcx]
0x180020165  mov     rax, [rax+8]
0x180020169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002016e  call    cs:__imp_GetCurrentThreadId
0x180020174  mov     [rbx+44h], eax
0x180020177  call    ?_InitializeFlyout@CTrayClock@@AEAAJXZ; CTrayClock::_InitializeFlyout(void)
0x18002017c  mov     [rbx+4Ch], eax
0x18002017f  test    eax, eax
0x180020181  js      short loc_18002018E
0x180020183  mov     rcx, rbx; this
0x180020186  call    ?_OpenUp@CTrayClock@@AEAAJXZ; CTrayClock::_OpenUp(void)
0x18002018b  mov     [rbx+48h], eax
0x18002018e  cmp     dword ptr [rbx+48h], 0
0x180020192  jge     short loc_1800201B0
0x180020194  mov     ecx, [rbx+44h]; idThread
0x180020197  xor     r9d, r9d; lParam
0x18002019a  xor     r8d, r8d; wParam
0x18002019d  lea     edx, [r9+12h]; Msg
0x1800201a1  call    cs:__imp_PostThreadMessageW
0x1800201a7  test    eax, eax
0x1800201a9  jnz     short loc_1800201B0
0x1800201ab  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800201b0  mov     rbx, [rsp+28h+arg_0]
0x1800201b5  xor     eax, eax
0x1800201b7  add     rsp, 20h
0x1800201bb  pop     rdi
0x1800201bc  retn
```
