# WapTpWorkItemCallback

- ea: `0x180058ec0`
- end: `0x18005900f`
- name: `WapTpWorkItemCallback`
- size: `335`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18002e460`
- `0x180058ec0`
- `0x180059018`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180058fd0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180058fd0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180058f30`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180058f4e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180058fa0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180058f30`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180058f4e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180058fa0`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180058ef6`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180058ef6`

## pseudocode

```c
void __fastcall WapTpWorkItemCallback(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  char v4; // si
  ULONG v5; // eax
  char v6; // cl
  ULONG v7; // eax
  void *v8; // rdx
  char v9; // di
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int LastError; // eax
  GUID ActivityId; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+40h] [rbp-10h]

  v16 = 0;
  ActivityId = 0;
  CallbackMayRunLong(Instance);
  v4 = Context[56];
  if ( v4 )
  {
    ActivityId = 0;
    v16 = 0;
    v5 = EventActivityIdControl(1u, &ActivityId);
    v6 = v16;
    if ( !v5 )
    {
      if ( (_BYTE)v16 )
        goto LABEL_9;
      v7 = EventActivityIdControl(2u, (LPGUID)(Context + 40));
      v6 = v16;
      if ( !v7 )
        v6 = 1;
      LOBYTE(v16) = v6;
    }
    if ( !v6 )
      ActivityId = 0;
  }
LABEL_9:
  v8 = (void *)*((_QWORD *)Context + 4);
  v9 = 0;
  if ( v8 )
  {
    if ( !SetThreadToken(0, v8) )
    {
      LastError = WaGetLastError(v12);
      if ( LastError )
        __fastfail(LastError);
    }
    v9 = 1;
  }
  (*((void (__fastcall **)(char *, _QWORD))Context + 2))(Context, *((_QWORD *)Context + 3));
  if ( v9 )
  {
    v13 = WaRevertToSelf(v11, v10);
    if ( v13 )
      __fastfail(v13);
  }
  if ( v4 )
  {
    if ( (_BYTE)v16 )
      EventActivityIdControl(2u, &ActivityId);
  }
}

```

## disassembly

```asm
0x180058ec0  mov     [rsp-18h+arg_10], rbx
0x180058ec5  mov     [rsp-18h+arg_18], rsi
0x180058eca  push    rbp
0x180058ecb  push    rdi
0x180058ecc  push    r14
0x180058ece  mov     rbp, rsp
0x180058ed1  sub     rsp, 50h
0x180058ed5  mov     rax, cs:__security_cookie
0x180058edc  xor     rax, rsp
0x180058edf  mov     [rbp+var_8], rax
0x180058ee3  xorps   xmm0, xmm0
0x180058ee6  xor     eax, eax
0x180058ee8  movups  [rbp+var_30], xmm0
0x180058eec  mov     [rbp+var_10], eax
0x180058eef  mov     rbx, rdx
0x180058ef2  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x180058ef6  call    cs:__imp_CallbackMayRunLong
0x180058efd  nop     dword ptr [rax+rax+00h]
0x180058f02  mov     sil, [rbx+38h]
0x180058f06  mov     r14d, 1
0x180058f0c  test    sil, sil
0x180058f0f  jz      short loc_180058F6B
0x180058f11  xorps   xmm0, xmm0
0x180058f14  lea     rdx, [rbp+ActivityId]; ActivityId
0x180058f18  xor     eax, eax
0x180058f1a  mov     ecx, r14d; ControlCode
0x180058f1d  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x180058f21  mov     [rbp+var_10], eax
0x180058f24  movups  xmm0, xmmword ptr [rbx+28h]
0x180058f28  mov     byte ptr [rbp+var_10], al
0x180058f2b  movdqu  [rbp+var_30], xmm0
0x180058f30  call    cs:__imp_EventActivityIdControl
0x180058f37  nop     dword ptr [rax+rax+00h]
0x180058f3c  mov     cl, byte ptr [rbp+var_10]
0x180058f3f  test    eax, eax
0x180058f41  jnz     short loc_180058F67
0x180058f43  test    cl, cl
0x180058f45  jnz     short loc_180058F6B
0x180058f47  lea     rdx, [rbx+28h]; ActivityId
0x180058f4b  lea     ecx, [rax+2]; ControlCode
0x180058f4e  call    cs:__imp_EventActivityIdControl
0x180058f55  nop     dword ptr [rax+rax+00h]
0x180058f5a  movzx   ecx, byte ptr [rbp+var_10]
0x180058f5e  test    eax, eax
0x180058f60  cmovz   ecx, r14d
0x180058f64  mov     byte ptr [rbp+var_10], cl
0x180058f67  test    cl, cl
0x180058f69  jz      short loc_180058FE5
0x180058f6b  mov     rdx, [rbx+20h]; Token
0x180058f6f  xor     dil, dil
0x180058f72  test    rdx, rdx
0x180058f75  jnz     short loc_180058FCE
0x180058f77  mov     rdx, [rbx+18h]
0x180058f7b  mov     rcx, rbx
0x180058f7e  mov     rax, [rbx+10h]
0x180058f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f87  test    dil, dil
0x180058f8a  jnz     short loc_180058FF1
0x180058f8c  test    sil, sil
0x180058f8f  jz      short loc_180058FAC
0x180058f91  cmp     byte ptr [rbp+var_10], 0
0x180058f95  jz      short loc_180058FAC
0x180058f97  lea     rdx, [rbp+ActivityId]; ActivityId
0x180058f9b  mov     ecx, 2; ControlCode
0x180058fa0  call    cs:__imp_EventActivityIdControl
0x180058fa7  nop     dword ptr [rax+rax+00h]
0x180058fac  mov     rcx, [rbp+var_8]
0x180058fb0  xor     rcx, rsp; StackCookie
0x180058fb3  call    __security_check_cookie
0x180058fb8  lea     r11, [rsp+50h+var_s0]
0x180058fbd  mov     rbx, [r11+30h]
0x180058fc1  mov     rsi, [r11+38h]
0x180058fc5  mov     rsp, r11
0x180058fc8  pop     r14
0x180058fca  pop     rdi
0x180058fcb  pop     rbp
0x180058fcc  retn
0x180058fce  xor     ecx, ecx; Thread
0x180058fd0  call    cs:__imp_SetThreadToken
0x180058fd7  nop     dword ptr [rax+rax+00h]
0x180058fdc  test    eax, eax
0x180058fde  jz      short loc_180059000
0x180058fe0  mov     dil, r14b
0x180058fe3  jmp     short loc_180058F77
0x180058fe5  xorps   xmm0, xmm0
0x180058fe8  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x180058fec  jmp     loc_180058F6B
0x180058ff1  call    WaRevertToSelf
0x180058ff6  test    eax, eax
0x180058ff8  jz      short loc_180058F8C
0x180058ffa  mov     ecx, eax
0x180058ffc  int     29h; Win8: RtlFailFast(ecx)
0x180058ffe  jmp     short loc_180058F8C
0x180059000  call    WaGetLastError
0x180059005  test    eax, eax
0x180059007  jz      short loc_180058FE0
0x180059009  mov     ecx, eax
0x18005900b  int     29h; Win8: RtlFailFast(ecx)
0x18005900d  jmp     short loc_180058FE0
```
