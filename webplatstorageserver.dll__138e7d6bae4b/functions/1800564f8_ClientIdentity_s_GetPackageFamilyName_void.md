# ClientIdentity::s_GetPackageFamilyName(void)

- ea: `0x1800564f8`
- end: `0x180056697`
- name: `?s_GetPackageFamilyName@ClientIdentity@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `415`
- prototype: `WCHAR *__fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f3cc`

## callees

- `0x18000f2b0`
- `0x180014b48`
- `0x180016b10`
- `0x1800564f8`
- `0x1800566a0`
- `0x180061c90`
- `0x18006c560`
- `0x180071f84`
- `0x180093f70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180056525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180056525`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005653f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005653f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005668e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005668e`
- `RPCRT4!RpcRevertToSelf` at `0x18005663b`
- `RPCRT4!RpcRevertToSelf` at `0x18005663b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800565f3`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800565f3`

## pseudocode

```c
WCHAR *__fastcall ClientIdentity::s_GetPackageFamilyName(WCHAR *a1)
{
  HANDLE CurrentThread; // rax
  const char *v3; // r9
  __int64 v4; // rdi
  __int64 v5; // r8
  _WORD *v6; // rdi
  __int64 i; // rcx
  WCHAR *v8; // r8
  unsigned int PackageFamilyNameFromToken; // eax
  unsigned __int64 v10; // rdx
  WCHAR *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  char v14; // [rsp+68h] [rbp+30h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+70h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+40h] BYREF

  TokenHandle = 0;
  RpcHelper::ImpersonateClient(&v14);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\clientidentity.cxx",
      v3);
  if ( v14 )
    RpcRevertToSelf();
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  v4 = std::wstring::_Calculate_growth(65, 7, 0x7FFFFFFFFFFFFFFELL);
  if ( (unsigned __int64)(v4 + 1) > 0x7FFFFFFFFFFFFFFFLL )
    std::_Throw_bad_array_new_length();
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(2 * (v4 + 1));
  *(_QWORD *)a1 = v5;
  *((_QWORD *)a1 + 2) = 65;
  *((_QWORD *)a1 + 3) = v4;
  v6 = (_WORD *)v5;
  for ( i = 65; i; --i )
    *v6++ = 0;
  *(_WORD *)(v5 + 130) = 0;
  packageFamilyNameLength = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(*((_QWORD *)a1 + 2));
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v8 = a1;
  else
    v8 = *(WCHAR **)a1;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(TokenHandle, &packageFamilyNameLength, v8);
  if ( PackageFamilyNameFromToken )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\clientidentity.cxx",
      (const char *)PackageFamilyNameFromToken,
      1u);
  v10 = packageFamilyNameLength - 1;
  if ( v10 > *((_QWORD *)a1 + 2) )
  {
    std::wstring::append(a1, v10 - *((_QWORD *)a1 + 2));
  }
  else
  {
    *((_QWORD *)a1 + 2) = v10;
    if ( *((_QWORD *)a1 + 3) <= 7u )
      v11 = a1;
    else
      v11 = *(WCHAR **)a1;
    v11[v10] = 0;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return a1;
}

```

## disassembly

```asm
0x1800564f8  mov     [rsp-20h+arg_0], rcx
0x1800564fd  push    rbp
0x1800564fe  push    rbx
0x1800564ff  push    rdi
0x180056500  push    r14
0x180056502  mov     rbp, rsp
0x180056505  sub     rsp, 38h
0x180056509  mov     rbx, rcx
0x18005650c  mov     [rbp+var_18], 0
0x180056513  mov     [rbp+TokenHandle], 0
0x18005651b  lea     rcx, [rbp+arg_8]
0x18005651f  call    ?ImpersonateClient@RpcHelper@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@PEAX@Z; RpcHelper::ImpersonateClient(void *)
0x180056524  nop
0x180056525  call    cs:__imp_GetCurrentThread
0x18005652b  mov     rdi, [rbp+20h]
0x18005652f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180056533  mov     edx, 8; DesiredAccess
0x180056538  lea     r8d, [rdx-7]; OpenAsSelf
0x18005653c  mov     rcx, rax; ThreadHandle
0x18005653f  call    cs:__imp_OpenThreadToken
0x180056545  test    eax, eax
0x180056547  jz      loc_180056664
0x18005654d  cmp     [rbp+arg_8], 0
0x180056551  jnz     loc_18005663B
0x180056557  xorps   xmm0, xmm0
0x18005655a  movups  xmmword ptr [rbx], xmm0
0x18005655d  mov     qword ptr [rbx+10h], 0
0x180056565  mov     qword ptr [rbx+18h], 0
0x18005656d  mov     edx, 7
0x180056572  mov     r8, 7FFFFFFFFFFFFFFEh
0x18005657c  lea     r14d, [rdx+3Ah]
0x180056580  mov     ecx, r14d
0x180056583  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180056588  mov     rdi, rax
0x18005658b  lea     rcx, [rax+1]
0x18005658f  mov     rax, 7FFFFFFFFFFFFFFFh
0x180056599  cmp     rcx, rax
0x18005659c  ja      loc_18005665E
0x1800565a2  add     rcx, rcx
0x1800565a5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800565aa  mov     r8, rax
0x1800565ad  mov     [rbx], rax
0x1800565b0  mov     [rbx+10h], r14
0x1800565b4  mov     [rbx+18h], rdi
0x1800565b8  xor     edx, edx
0x1800565ba  movzx   eax, dx
0x1800565bd  mov     rdi, r8
0x1800565c0  mov     ecx, r14d
0x1800565c3  rep stosw
0x1800565c6  mov     [r8+82h], dx
0x1800565ce  mov     [rbp+var_18], 1
0x1800565d5  mov     rcx, [rbx+10h]
0x1800565d9  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x1800565de  mov     [rbp+packageFamilyNameLength], eax
0x1800565e1  cmp     qword ptr [rbx+18h], 7
0x1800565e6  jbe     short loc_18005664B
0x1800565e8  mov     r8, [rbx]; packageFamilyName
0x1800565eb  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x1800565ef  mov     rcx, [rbp+TokenHandle]; token
0x1800565f3  call    cs:__imp_GetPackageFamilyNameFromToken
0x1800565f9  mov     rcx, [rbp+20h]; this
0x1800565fd  test    eax, eax
0x1800565ff  jnz     short loc_180056679
0x180056601  mov     edx, [rbp+packageFamilyNameLength]
0x180056604  dec     edx
0x180056606  cmp     rdx, [rbx+10h]
0x18005660a  ja      short loc_180056650
0x18005660c  mov     [rbx+10h], rdx
0x180056610  cmp     qword ptr [rbx+18h], 7
0x180056615  jbe     short loc_180056646
0x180056617  mov     rcx, [rbx]
0x18005661a  xor     eax, eax
0x18005661c  mov     [rcx+rdx*2], ax
0x180056620  mov     rcx, [rbp+TokenHandle]; hObject
0x180056624  lea     rax, [rcx-1]
0x180056628  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005662c  jbe     short loc_18005668E
0x18005662e  mov     rax, rbx
0x180056631  add     rsp, 38h
0x180056635  pop     r14
0x180056637  pop     rdi
0x180056638  pop     rbx
0x180056639  pop     rbp
0x18005663a  retn
0x18005663b  call    cs:__imp_RpcRevertToSelf
0x180056641  jmp     loc_180056557
0x180056646  mov     rcx, rbx
0x180056649  jmp     short loc_18005661A
0x18005664b  mov     r8, rbx
0x18005664e  jmp     short loc_1800565EB
0x180056650  sub     rdx, [rbx+10h]
0x180056654  mov     rcx, rbx
0x180056657  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18005665c  jmp     short loc_180056620
0x18005665e  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180056664  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\webplatstorageser"...
0x18005666b  mov     edx, 62h ; 'b'; void *
0x180056670  mov     rcx, rdi; this
0x180056673  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180056679  mov     r9d, eax; char *
0x18005667c  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\webplatstorageser"...
0x180056683  mov     edx, 67h ; 'g'; void *
0x180056688  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005668e  call    cs:__imp_CloseHandle
0x180056694  jmp     short loc_18005662E
```
