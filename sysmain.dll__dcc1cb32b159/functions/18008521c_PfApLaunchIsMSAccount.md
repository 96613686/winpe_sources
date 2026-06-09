# PfApLaunchIsMSAccount

- ea: `0x18008521c`
- end: `0x180085311`
- name: `PfApLaunchIsMSAccount`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006d810`

## callees

- `0x18008521c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800852f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800852f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085301`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085279`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085279`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800852e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800852e3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18008526b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18008526b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800852a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800852a2`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180085245`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180085245`

## pseudocode

```c
__int64 __fastcall PfApLaunchIsMSAccount(__int64 a1)
{
  __int64 v1; // rcx
  BOOL v2; // edi
  unsigned int v3; // ebx
  int v5; // [rsp+50h] [rbp+20h] BYREF
  HANDLE hExistingToken; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+38h] BYREF

  v1 = *(unsigned int *)(a1 + 80);
  v2 = 0;
  ppv = 0;
  hExistingToken = 0;
  v3 = 0;
  hObject = 0;
  v5 = 0;
  if ( (unsigned int)QueryUserToken(v1, &hExistingToken) )
  {
    if ( DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
    {
      v2 = ImpersonateLoggedOnUser(hExistingToken);
      if ( v2 )
      {
        if ( CoCreateInstance(&CLSID_CoClassWindowsLiveProvider, 0, 1u, &IID_IConnectedIdentityProvider, &ppv) >= 0
          && (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 40LL))(ppv, &v5) >= 0 )
        {
          LOBYTE(v3) = v5 != 0;
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v2 )
    RevertToSelf();
  if ( hExistingToken )
    CloseHandle(hExistingToken);
  if ( hObject )
    CloseHandle(hObject);
  return v3;
}

```

## disassembly

```asm
0x18008521c  push    rbp
0x18008521e  push    rbx
0x18008521f  push    rdi
0x180085220  mov     rbp, rsp
0x180085223  sub     rsp, 30h
0x180085227  mov     ecx, [rcx+50h]
0x18008522a  lea     rdx, [rbp+hExistingToken]
0x18008522e  xor     edi, edi
0x180085230  mov     [rbp+ppv], 0
0x180085238  mov     [rbp+hExistingToken], rdi
0x18008523c  xor     ebx, ebx
0x18008523e  mov     [rbp+hObject], rdi
0x180085242  mov     [rbp+arg_0], edi
0x180085245  call    cs:__imp_QueryUserToken
0x18008524b  test    eax, eax
0x18008524d  jz      short loc_1800852CA
0x18008524f  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x180085253  lea     rax, [rbp+hObject]
0x180085257  lea     r9d, [rdi+2]; ImpersonationLevel
0x18008525b  mov     [rsp+30h+phNewToken], rax; phNewToken
0x180085260  xor     r8d, r8d; lpTokenAttributes
0x180085263  mov     [rsp+30h+TokenType], r9d; TokenType
0x180085268  lea     edx, [rdi+0Ch]; dwDesiredAccess
0x18008526b  call    cs:__imp_DuplicateTokenEx
0x180085271  test    eax, eax
0x180085273  jz      short loc_1800852CA
0x180085275  mov     rcx, [rbp+hExistingToken]; hToken
0x180085279  call    cs:__imp_ImpersonateLoggedOnUser
0x18008527f  mov     edi, eax
0x180085281  test    eax, eax
0x180085283  jz      short loc_1800852CA
0x180085285  lea     rax, [rbp+ppv]
0x180085289  xor     edx, edx; pUnkOuter
0x18008528b  lea     r9, IID_IConnectedIdentityProvider; riid
0x180085292  mov     qword ptr [rsp+30h+TokenType], rax; ppv
0x180085297  lea     r8d, [rbx+1]; dwClsContext
0x18008529b  lea     rcx, CLSID_CoClassWindowsLiveProvider; rclsid
0x1800852a2  call    cs:__imp_CoCreateInstance
0x1800852a8  test    eax, eax
0x1800852aa  js      short loc_1800852CA
0x1800852ac  mov     rcx, [rbp+ppv]
0x1800852b0  lea     rdx, [rbp+arg_0]
0x1800852b4  mov     rax, [rcx]
0x1800852b7  mov     rax, [rax+28h]
0x1800852bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800852c0  test    eax, eax
0x1800852c2  js      short loc_1800852CA
0x1800852c4  cmp     [rbp+arg_0], ebx
0x1800852c7  setnz   bl
0x1800852ca  mov     rcx, [rbp+ppv]
0x1800852ce  test    rcx, rcx
0x1800852d1  jz      short loc_1800852DF
0x1800852d3  mov     rax, [rcx]
0x1800852d6  mov     rax, [rax+10h]
0x1800852da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800852df  test    edi, edi
0x1800852e1  jz      short loc_1800852E9
0x1800852e3  call    cs:__imp_RevertToSelf
0x1800852e9  mov     rcx, [rbp+hExistingToken]; hObject
0x1800852ed  test    rcx, rcx
0x1800852f0  jz      short loc_1800852F8
0x1800852f2  call    cs:__imp_CloseHandle
0x1800852f8  mov     rcx, [rbp+hObject]; hObject
0x1800852fc  test    rcx, rcx
0x1800852ff  jz      short loc_180085307
0x180085301  call    cs:__imp_CloseHandle
0x180085307  mov     eax, ebx
0x180085309  add     rsp, 30h
0x18008530d  pop     rdi
0x18008530e  pop     rbx
0x18008530f  pop     rbp
0x180085310  retn
```
