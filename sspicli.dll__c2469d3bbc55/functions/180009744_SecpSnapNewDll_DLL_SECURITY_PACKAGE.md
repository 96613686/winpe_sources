# SecpSnapNewDll(_DLL_SECURITY_PACKAGE *)

- ea: `0x180009744`
- end: `0x1800098a6`
- name: `?SecpSnapNewDll@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct _DLL_SECURITY_PACKAGE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800069d8`
- `0x180008fc4`

## callees

- `0x180009744`
- `0x18001d360`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800097d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009830`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800097d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800097bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800097bf`

## pseudocode

```c
__int64 __fastcall SecpSnapNewDll(struct _DLL_SECURITY_PACKAGE *a1, __int64 a2, int a3)
{
  __int64 v4; // rsi
  HMODULE *v5; // rdi
  FARPROC ProcAddress; // rax
  int v8; // r14d
  int v9; // [rsp+78h] [rbp+10h] BYREF
  __int64 v10; // [rsp+80h] [rbp+18h]
  __int64 v11; // [rsp+88h] [rbp+20h]

  v9 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_IS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_QWORD *)(*((_QWORD *)a1 + 7) + 24LL),
      a3,
      *((_QWORD *)a1 + 3),
      *(_QWORD *)(*((_QWORD *)a1 + 7) + 24LL));
  v4 = *((_QWORD *)a1 + 7);
  v11 = v4;
  v5 = (HMODULE *)(v4 + 8);
  if ( (_UNKNOWN *)v4 == &SecpBuiltinBinding )
    ProcAddress = (FARPROC)NegUserModeInitialize;
  else
    ProcAddress = GetProcAddress(*v5, "SpUserModeInitialize");
  v10 = v4 + 8;
  if ( ProcAddress )
  {
    v8 = ((__int64 (__fastcall *)(__int64, int *, __int64, __int64))ProcAddress)(0x10000, &v9, v4 + 48, v4 + 36);
    if ( v8 >= 0 )
    {
      *((_QWORD *)a1 + 23) = *(_QWORD *)(v4 + 48) + 120LL * *((unsigned int *)a1 + 8);
      *((_QWORD *)a1 + 21) = &LsaFunctionTable;
      *((_QWORD *)a1 + 20) = LsaFunctionTableA;
      *((_QWORD *)a1 + 22) = &LsaFunctionTable;
      *((_QWORD *)a1 + 24) = LsaBootPackage;
      *((_QWORD *)a1 + 25) = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
      *((_DWORD *)a1 + 22) = v9;
      return 0;
    }
    else
    {
      FreeLibrary(*v5);
      *v5 = 0;
      return (unsigned int)v8;
    }
  }
  else
  {
    FreeLibrary(*v5);
    *v5 = 0;
    return 2148074245LL;
  }
}

```

## disassembly

```asm
0x180009744  mov     [rsp+arg_0], rcx
0x180009749  push    rbx
0x18000974a  push    rsi
0x18000974b  push    rdi
0x18000974c  push    r14
0x18000974e  sub     rsp, 48h
0x180009752  mov     rbx, rcx
0x180009755  mov     [rsp+68h+arg_8], 0
0x18000975d  lea     rax, WPP_GLOBAL_Control
0x180009764  mov     rcx, cs:WPP_GLOBAL_Control
0x18000976b  cmp     rcx, rax
0x18000976e  jz      short loc_180009790
0x180009770  test    byte ptr [rcx+1Ch], 4
0x180009774  jz      short loc_180009790
0x180009776  mov     rax, [rbx+38h]
0x18000977a  mov     rdx, [rax+18h]
0x18000977e  mov     [rsp+68h+var_48], rdx
0x180009783  mov     r9, [rbx+18h]
0x180009787  mov     rcx, [rcx+10h]
0x18000978b  call    WPP_SF_IS
0x180009790  mov     rsi, [rbx+38h]
0x180009794  mov     [rsp+68h+arg_18], rsi
0x18000979c  lea     rax, ?SecpBuiltinBinding@@3U_SECP_DLL_BINDING@@A; _SECP_DLL_BINDING SecpBuiltinBinding
0x1800097a3  lea     rdi, [rsi+8]
0x1800097a7  cmp     rsi, rax
0x1800097aa  jnz     short loc_1800097B5
0x1800097ac  lea     rax, ?NegUserModeInitialize@@YAJKPEAKPEAPEAU_SECPKG_USER_FUNCTION_TABLE@@0@Z; NegUserModeInitialize(ulong,ulong *,_SECPKG_USER_FUNCTION_TABLE * *,ulong *)
0x1800097b3  jmp     short loc_1800097C5
0x1800097b5  lea     rdx, ProcName; "SpUserModeInitialize"
0x1800097bc  mov     rcx, [rdi]; hModule
0x1800097bf  call    cs:__imp_GetProcAddress
0x1800097c5  mov     [rsp+68h+arg_10], rdi
0x1800097cd  test    rax, rax
0x1800097d0  jnz     short loc_1800097EC
0x1800097d2  mov     rcx, [rdi]; hLibModule
0x1800097d5  call    cs:__imp_FreeLibrary
0x1800097db  mov     qword ptr [rdi], 0
0x1800097e2  mov     eax, 80090305h
0x1800097e7  jmp     loc_18000989C
0x1800097ec  lea     r9, [rsi+24h]
0x1800097f0  lea     r8, [rsi+30h]
0x1800097f4  lea     rdx, [rsp+68h+arg_8]
0x1800097f9  mov     ecx, 10000h
0x1800097fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009803  mov     r14d, eax
0x180009806  mov     [rsp+68h+var_38], eax
0x18000980a  jmp     short loc_180009828
0x18000980c  mov     r14d, eax
0x18000980f  mov     [rsp+68h+var_38], eax
0x180009813  mov     rbx, [rsp+68h+arg_0]
0x180009818  mov     rdi, [rsp+68h+arg_10]
0x180009820  mov     rsi, [rsp+68h+arg_18]
0x180009828  test    r14d, r14d
0x18000982b  jns     short loc_180009842
0x18000982d  mov     rcx, [rdi]; hLibModule
0x180009830  call    cs:__imp_FreeLibrary
0x180009836  mov     qword ptr [rdi], 0
0x18000983d  mov     eax, r14d
0x180009840  jmp     short loc_18000989C
0x180009842  mov     eax, [rbx+20h]
0x180009845  imul    rcx, rax, 78h ; 'x'
0x180009849  add     rcx, [rsi+30h]
0x18000984d  mov     [rbx+0B8h], rcx
0x180009854  lea     rcx, LsaFunctionTable
0x18000985b  mov     [rbx+0A8h], rcx
0x180009862  lea     rax, LsaFunctionTableA
0x180009869  mov     [rbx+0A0h], rax
0x180009870  mov     [rbx+0B0h], rcx
0x180009877  lea     rax, LsaBootPackage
0x18000987e  mov     [rbx+0C0h], rax
0x180009885  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18000988c  mov     [rbx+0C8h], rax
0x180009893  mov     eax, [rsp+68h+arg_8]
0x180009897  mov     [rbx+58h], eax
0x18000989a  xor     eax, eax
0x18000989c  add     rsp, 48h
0x1800098a0  pop     r14
0x1800098a2  pop     rdi
0x1800098a3  pop     rsi
0x1800098a4  pop     rbx
0x1800098a5  retn
```
