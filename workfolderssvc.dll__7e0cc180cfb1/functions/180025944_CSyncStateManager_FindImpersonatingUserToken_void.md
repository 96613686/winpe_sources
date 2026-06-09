# CSyncStateManager::FindImpersonatingUserToken(void)

- ea: `0x180025944`
- end: `0x180025a2e`
- name: `?FindImpersonatingUserToken@CSyncStateManager@@CAPEAXXZ`
- size: `234`
- prototype: `void *(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180023e64`
- `0x180025850`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x180025944`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800259c4`
- `KERNEL32!GetCurrentThread` at `0x1800259c4`
- `ADVAPI32!OpenThreadToken` at `0x1800259d8`
- `ADVAPI32!OpenThreadToken` at `0x1800259d8`

## string_xrefs

- `0x1800259ab`: `CSyncStateManager::FindImpersonatingUserToken`

## pseudocode

```c
void *CSyncStateManager::FindImpersonatingUserToken(void)
{
  _BYTE *v0; // rax
  char v1; // cl
  HANDLE CurrentThread; // rax
  void *v3; // rbx
  void *TokenHandle; // [rsp+20h] [rbp-30h] BYREF
  int LastFailureAsHRESULT; // [rsp+28h] [rbp-28h] BYREF
  int v7; // [rsp+2Ch] [rbp-24h]
  char v8; // [rsp+30h] [rbp-20h]
  const char *v9; // [rsp+38h] [rbp-18h]
  __int64 v10; // [rsp+40h] [rbp-10h]
  int pExceptionObject; // [rsp+60h] [rbp+10h] BYREF

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( (v0[68] & 8) == 0 || (v1 = 1, v0[65] < 6u) )
    v1 = 0;
  v7 = 781;
  v8 = v1;
  v9 = "CSyncStateManager::FindImpersonatingUserToken";
  v10 = 0;
  TokenHandle = 0;
  LastFailureAsHRESULT = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v7) = 787;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v7) = 787;
  v3 = TokenHandle;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return v3;
}

```

## disassembly

```asm
0x180025944  mov     [rsp-8+arg_8], rbx
0x180025949  push    rbp
0x18002594a  mov     rbp, rsp
0x18002594d  sub     rsp, 50h
0x180025951  lea     rcx, WPP_GLOBAL_Control
0x180025958  mov     rax, cs:WPP_GLOBAL_Control
0x18002595f  cmp     rax, rcx
0x180025962  jz      short loc_18002598C
0x180025964  test    byte ptr [rax+44h], 8
0x180025968  jz      short loc_18002598C
0x18002596a  cmp     byte ptr [rax+41h], 6
0x18002596e  jb      short loc_18002598C
0x180025970  mov     edx, 2Ch ; ','
0x180025975  lea     r8, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids
0x18002597c  mov     rcx, [rax+38h]
0x180025980  call    WPP_SF_
0x180025985  mov     rax, cs:WPP_GLOBAL_Control
0x18002598c  xor     ebx, ebx
0x18002598e  test    byte ptr [rax+44h], 8
0x180025992  jz      short loc_18002599C
0x180025994  cmp     byte ptr [rax+41h], 6
0x180025998  mov     cl, 1
0x18002599a  jnb     short loc_18002599E
0x18002599c  mov     cl, bl
0x18002599e  mov     [rbp+var_28], ebx
0x1800259a1  mov     [rbp+var_24], 30Dh
0x1800259a8  mov     [rbp+var_20], cl
0x1800259ab  lea     rax, aCsyncstatemana_12; "CSyncStateManager::FindImpersonatingUse"...
0x1800259b2  mov     [rbp+var_18], rax
0x1800259b6  mov     [rbp+var_10], rbx
0x1800259ba  mov     [rbp+TokenHandle], rbx
0x1800259be  mov     eax, [rbp+var_28]
0x1800259c1  mov     [rbp+var_28], eax
0x1800259c4  call    cs:__imp_GetCurrentThread
0x1800259ca  mov     rcx, rax; ThreadHandle
0x1800259cd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800259d1  xor     r8d, r8d; OpenAsSelf
0x1800259d4  lea     edx, [r8+0Ch]; DesiredAccess
0x1800259d8  call    cs:__imp_OpenThreadToken
0x1800259de  test    eax, eax
0x1800259e0  jnz     short loc_180025A07
0x1800259e2  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800259e7  mov     [rbp+var_28], eax
0x1800259ea  mov     ecx, 313h
0x1800259ef  mov     word ptr [rbp+var_24+2], cx
0x1800259f3  mov     [rbp+pExceptionObject], eax
0x1800259f6  lea     rdx, _TI1J; pThrowInfo
0x1800259fd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025a01  call    _CxxThrowException_0
0x180025a07  mov     [rbp+var_28], ebx
0x180025a0a  mov     ecx, 313h
0x180025a0f  mov     word ptr [rbp+var_24], cx
0x180025a13  mov     rbx, [rbp+TokenHandle]
0x180025a17  lea     rcx, [rbp+var_28]; this
0x180025a1b  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180025a20  mov     rax, rbx
0x180025a23  mov     rbx, [rsp+50h+arg_8]
0x180025a28  add     rsp, 50h
0x180025a2c  pop     rbp
0x180025a2d  retn
```
