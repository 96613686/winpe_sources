# WaTpInitializeWorkItem

- ea: `0x18002e1a4`
- end: `0x18002e2be`
- name: `WaTpInitializeWorkItem`
- size: `282`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18007d048`
- `0x180081a90`
- `0x18008e09c`

## callees

- `0x180014f30`
- `0x18002e1a4`
- `0x18002e460`
- `0x1800722f0`
- `0x180072c70`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e23d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e23d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e1f3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e1f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002e293`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002e293`

## pseudocode

```c
__int64 __fastcall WaTpInitializeWorkItem(char *pv, __int64 a2, __int64 a3, char a4)
{
  PTP_WORK ThreadpoolWork; // rax
  __int64 v9; // rcx
  HANDLE *v10; // rbx
  unsigned int CurrentThreadToken; // edi
  struct _TP_WORK *v13; // rcx

  memset_0(pv, 0, 0x40u);
  *(_DWORD *)pv = 1331122260;
  ThreadpoolWork = CreateThreadpoolWork(WapTpWorkItemCallback, pv, &WaTpEnvironment);
  *((_QWORD *)pv + 1) = ThreadpoolWork;
  v10 = (HANDLE *)(pv + 32);
  if ( ThreadpoolWork )
  {
    *((_QWORD *)pv + 2) = a2;
    *((_QWORD *)pv + 3) = a3;
    *v10 = 0;
    if ( !a4 )
      return 0;
    CurrentThreadToken = WaGetCurrentThreadToken((__int64 *)pv + 4);
    if ( !CurrentThreadToken )
    {
      if ( EventActivityIdControl(1u, (LPGUID)(pv + 40)) )
        *(_OWORD *)(pv + 40) = 0;
      pv[56] = 1;
      return 0;
    }
    *v10 = 0;
  }
  else
  {
    CurrentThreadToken = WaGetLastError(v9);
    if ( !CurrentThreadToken )
      return CurrentThreadToken;
  }
  v13 = (struct _TP_WORK *)*((_QWORD *)pv + 1);
  if ( v13 )
    CloseThreadpoolWork(v13);
  if ( *v10 )
    CloseHandle(*v10);
  return CurrentThreadToken;
}

```

## disassembly

```asm
0x18002e1a4  mov     [rsp+arg_8], rbx
0x18002e1a9  mov     [rsp+arg_10], rbp
0x18002e1ae  push    rsi
0x18002e1af  push    rdi
0x18002e1b0  push    r14
0x18002e1b2  sub     rsp, 40h
0x18002e1b6  mov     rax, cs:__security_cookie
0x18002e1bd  xor     rax, rsp
0x18002e1c0  mov     [rsp+58h+var_28], rax
0x18002e1c5  mov     r14, rdx
0x18002e1c8  mov     rbp, r8
0x18002e1cb  xor     edx, edx; Val
0x18002e1cd  mov     dil, r9b
0x18002e1d0  mov     rsi, rcx
0x18002e1d3  lea     r8d, [rdx+40h]; Size
0x18002e1d7  call    memset_0
0x18002e1dc  lea     r8, WaTpEnvironment; pcbe
0x18002e1e3  mov     dword ptr [rsi], 4F575054h
0x18002e1e9  mov     rdx, rsi; pv
0x18002e1ec  lea     rcx, WapTpWorkItemCallback; pfnwk
0x18002e1f3  call    cs:__imp_CreateThreadpoolWork
0x18002e1fa  nop     dword ptr [rax+rax+00h]
0x18002e1ff  mov     [rsi+8], rax
0x18002e203  lea     rbx, [rsi+20h]
0x18002e207  test    rax, rax
0x18002e20a  jz      short loc_18002E255
0x18002e20c  mov     [rsi+10h], r14
0x18002e210  mov     [rsi+18h], rbp
0x18002e214  mov     qword ptr [rbx], 0
0x18002e21b  test    dil, dil
0x18002e21e  jz      short loc_18002E251
0x18002e220  mov     rcx, rbx
0x18002e223  call    WaGetCurrentThreadToken
0x18002e228  mov     edi, eax
0x18002e22a  test    eax, eax
0x18002e22c  jnz     short loc_18002E283
0x18002e22e  xorps   xmm0, xmm0
0x18002e231  lea     rdx, [rsi+28h]; ActivityId
0x18002e235  lea     ecx, [rax+1]; ControlCode
0x18002e238  movups  [rsp+58h+var_38], xmm0
0x18002e23d  call    cs:__imp_EventActivityIdControl
0x18002e244  nop     dword ptr [rax+rax+00h]
0x18002e249  test    eax, eax
0x18002e24b  jnz     short loc_18002E2B5
0x18002e24d  mov     byte ptr [rsi+38h], 1
0x18002e251  xor     edi, edi
0x18002e253  jmp     short loc_18002E260
0x18002e255  call    WaGetLastError
0x18002e25a  mov     edi, eax
0x18002e25c  test    eax, eax
0x18002e25e  jnz     short loc_18002E28A
0x18002e260  mov     eax, edi
0x18002e262  mov     rcx, [rsp+58h+var_28]
0x18002e267  xor     rcx, rsp; StackCookie
0x18002e26a  call    __security_check_cookie
0x18002e26f  mov     rbx, [rsp+58h+arg_8]
0x18002e274  mov     rbp, [rsp+58h+arg_10]
0x18002e279  add     rsp, 40h
0x18002e27d  pop     r14
0x18002e27f  pop     rdi
0x18002e280  pop     rsi
0x18002e281  retn
0x18002e283  mov     qword ptr [rbx], 0
0x18002e28a  mov     rcx, [rsi+8]; pwk
0x18002e28e  test    rcx, rcx
0x18002e291  jz      short loc_18002E29F
0x18002e293  call    cs:__imp_CloseThreadpoolWork
0x18002e29a  nop     dword ptr [rax+rax+00h]
0x18002e29f  mov     rcx, [rbx]; hObject
0x18002e2a2  test    rcx, rcx
0x18002e2a5  jz      short loc_18002E260
0x18002e2a7  call    cs:__imp_CloseHandle
0x18002e2ae  nop     dword ptr [rax+rax+00h]
0x18002e2b3  jmp     short loc_18002E260
0x18002e2b5  xorps   xmm0, xmm0
0x18002e2b8  movups  xmmword ptr [rsi+28h], xmm0
0x18002e2bc  jmp     short loc_18002E24D
```
