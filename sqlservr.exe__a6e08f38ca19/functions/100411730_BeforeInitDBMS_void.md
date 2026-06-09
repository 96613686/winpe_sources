# BeforeInitDBMS(void)

- ea: `0x100411730`
- end: `0x1004118b9`
- name: `?BeforeInitDBMS@@YAXXZ`
- size: `393`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x100411730`
- `0x1004403d0`
- `0x100440a70`

## import_xrefs

- `sqlmin!?Init@CFeatureSwitchesSbs@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100411775`
- `sqlmin!?Init@CFeatureSwitchesSbs@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100411775`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041173a`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004117a4`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041182b`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041173a`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004117a4`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041182b`
- `sqlmin!GetXdbServerGlobals` at `0x1004117c3`
- `sqlmin!GetXdbServerGlobals` at `0x1004117c3`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041179e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041189c`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041179e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041189c`
- `sqlfederation!InitFederation` at `0x100411877`
- `sqlfederation!InitFederation` at `0x100411877`
- `sqlfabric!?ResolveFabricURIToNodeId@@YAJPEAVIMemObj@@PEA_WKPEBVSOS_WaitInfo@@P6APEAX1PEAX@Z3_N@Z` at `0x100411802`
- `sqlfabric!?ResolveFabricURIToEndpointAsync@@YAJPEAVIMemObj@@PEA_WKPEBVSOS_WaitInfo@@PEB_WK3KP6APEAX1PEAX@Z4_N@Z` at `0x10041176d`
- `sbs!?InitSbsStorage@@YA_NP6AJPEAVIMemObj@@PEA_WKPEBVSOS_WaitInfo@@PEB_WK3KP6APEAX1PEAX@Z4_N@Z@Z` at `0x10041177e`
- `sbs!?InitSbsStorage@@YA_NP6AJPEAVIMemObj@@PEA_WKPEBVSOS_WaitInfo@@PEB_WK3KP6APEAX1PEAX@Z4_N@Z@Z` at `0x10041177e`

## string_xrefs

- `0x10041185b`: `DWResultCacheDb`
- `0x1004118a2`: `Federation Initialization Completed Successfully \n`

## pseudocode

```c
void BeforeInitDBMS(void)
{
  int (*v0)(struct IMemObj *, wchar_t *, unsigned int, const struct SOS_WaitInfo *, const wchar_t *, unsigned int, const wchar_t *, unsigned int, void *(*)(wchar_t *, void *), void *, bool); // rbx
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // rax
  _DWORD (*v4)(struct IMemObj *, wchar_t *, unsigned int, const struct SOS_WaitInfo *, void *(*)(wchar_t *, void *), void *, bool); // rdi
  int v5; // ebx
  char v6; // al
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r9

  if ( *(_BYTE *)(CFeatureSwitchesMin::ExportCurrentInstance() + 112)
    || (*(_BYTE *)(qword_10049F340 + 1262) & 0x20) != 0 )
  {
    v0 = 0;
    if ( *((_DWORD *)qword_10049F360 + 3626) )
      v0 = ResolveFabricURIToEndpointAsync;
    CFeatureSwitchesSbs::Init(1);
    if ( !InitSbsStorage(v0) )
    {
      scierrlog(0x42F2u, L"SQL tiered storage");
      SQLExit(42);
    }
  }
  if ( !*(_BYTE *)(CFeatureSwitchesMin::ExportCurrentInstance() + 604) )
  {
    v3 = qword_10049F340;
    if ( (*(_BYTE *)(qword_10049F340 + 1488) & 8) == 0 )
    {
LABEL_11:
      if ( (*(_BYTE *)(v3 + 1487) & 0x10) == 0 )
        return;
      goto LABEL_12;
    }
  }
  if ( *(_BYTE *)(GetXdbServerGlobals(v2, v1) + 12004) )
  {
    v3 = qword_10049F340;
    goto LABEL_11;
  }
LABEL_12:
  v4 = 0;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
    v4 = ResolveFabricURIToNodeId;
  traceprint(L"Initializing Federation.\n");
  v5 = ((unsigned __int8)~*(_BYTE *)(qword_10049F340 + 1487) >> 5) | 0xFFFE;
  if ( *(_BYTE *)(CFeatureSwitchesMin::ExportCurrentInstance() + 604) || (*(_BYTE *)(qword_10049F340 + 1488) & 8) != 0 )
  {
    v6 = 1;
    v5 = 10;
  }
  else
  {
    v6 = 0;
  }
  v7 = L"DWResultCacheDb";
  if ( !v6 )
    v7 = 0;
  v8 = L"DWShellDb";
  if ( !v6 )
    v8 = 0;
  if ( (int)InitFederation(v4, v7, v7, v8, v5) < 0 )
  {
    scierrlog(0x42F2u, L"SQL federation");
    SQLExit(43);
  }
  traceprint(L"Federation Initialization Completed Successfully \n");
}

```

## disassembly

```asm
0x100411730  mov     [rsp+arg_8], rbx
0x100411735  push    rsi
0x100411736  sub     rsp, 30h
0x10041173a  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::ExportCurrentInstance(void)
0x100411740  xor     esi, esi
0x100411742  cmp     [rax+70h], sil
0x100411746  jnz     short loc_100411758
0x100411748  mov     rax, cs:qword_10049F340
0x10041174f  test    byte ptr [rax+4EEh], 20h
0x100411756  jz      short loc_1004117A4
0x100411758  mov     rax, cs:qword_10049F360
0x10041175f  mov     rbx, rsi
0x100411762  mov     ecx, 1
0x100411767  cmp     [rax+38A8h], ebx
0x10041176d  cmovnz  rbx, cs:__imp_?ResolveFabricURIToEndpointAsync@@YAJPEAVIMemObj@@PEA_WKPEBVSOS_WaitInfo@@PEB_WK3KP6APEAX1PEAX@Z4_N@Z; ResolveFabricURIToEndpointAsync(IMemObj *,wchar_t *,ulong,SOS_WaitInfo const *,wchar_t const *,ulong,wchar_t const *,ulong,void * (*)(wchar_t *,void *),void *,bool)
0x100411775  call    cs:__imp_?Init@CFeatureSwitchesSbs@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesSbs::Init(CFeatureSwitchesExecEnv)
0x10041177b  mov     rcx, rbx
0x10041177e  call    cs:__imp_?InitSbsStorage@@YA_NP6AJPEAVIMemObj@@PEA_WKPEBVSOS_WaitInfo@@PEB_WK3KP6APEAX1PEAX@Z4_N@Z@Z; InitSbsStorage(long (*)(IMemObj *,wchar_t *,ulong,SOS_WaitInfo const *,wchar_t const *,ulong,wchar_t const *,ulong,void * (*)(wchar_t *,void *),void *,bool))
0x100411784  test    al, al
0x100411786  jnz     short loc_1004117A4
0x100411788  lea     rdx, aSqlTieredStora; "SQL tiered storage"
0x10041178f  mov     ecx, 42F2h; unsigned int
0x100411794  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100411799  mov     ecx, 2Ah ; '*'
0x10041179e  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x1004117a4  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::ExportCurrentInstance(void)
0x1004117aa  cmp     [rax+25Ch], sil
0x1004117b1  jnz     short loc_1004117C3
0x1004117b3  mov     rax, cs:qword_10049F340
0x1004117ba  test    byte ptr [rax+5D0h], 8
0x1004117c1  jz      short loc_1004117D9
0x1004117c3  call    cs:__imp_GetXdbServerGlobals
0x1004117c9  cmp     [rax+2EE4h], sil
0x1004117d0  jz      short loc_1004117E6
0x1004117d2  mov     rax, cs:qword_10049F340
0x1004117d9  test    byte ptr [rax+5CFh], 10h
0x1004117e0  jz      loc_1004118AE
0x1004117e6  mov     rax, cs:qword_10049F360
0x1004117ed  lea     rcx, aInitializingFe; "Initializing Federation.\n"
0x1004117f4  mov     [rsp+38h+arg_0], rdi
0x1004117f9  mov     rdi, rsi
0x1004117fc  cmp     [rax+38A8h], esi
0x100411802  cmovnz  rdi, cs:__imp_?ResolveFabricURIToNodeId@@YAJPEAVIMemObj@@PEA_WKPEBVSOS_WaitInfo@@P6APEAX1PEAX@Z3_N@Z; ResolveFabricURIToNodeId(IMemObj *,wchar_t *,ulong,SOS_WaitInfo const *,void * (*)(wchar_t *,void *),void *,bool)
0x10041180a  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x10041180f  mov     rax, cs:qword_10049F340
0x100411816  movzx   ecx, byte ptr [rax+5CFh]
0x10041181d  not     cl
0x10041181f  movzx   ebx, cl
0x100411822  shr     ebx, 5
0x100411825  or      ebx, 0FFFEh
0x10041182b  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::ExportCurrentInstance(void)
0x100411831  cmp     [rax+25Ch], sil
0x100411838  jnz     short loc_10041184E
0x10041183a  mov     rax, cs:qword_10049F340
0x100411841  test    byte ptr [rax+5D0h], 8
0x100411848  jnz     short loc_10041184E
0x10041184a  xor     al, al
0x10041184c  jmp     short loc_100411855
0x10041184e  mov     al, 1
0x100411850  mov     ebx, 0Ah
0x100411855  test    al, al
0x100411857  mov     [rsp+38h+var_18], ebx
0x10041185b  lea     rdx, aDwresultcached; "DWResultCacheDb"
0x100411862  mov     rcx, rdi
0x100411865  cmovz   rdx, rsi
0x100411869  lea     r9, aDwshelldb; "DWShellDb"
0x100411870  mov     r8, rdx
0x100411873  cmovz   r9, rsi
0x100411877  call    cs:__imp_InitFederation
0x10041187d  mov     rdi, [rsp+38h+arg_0]
0x100411882  test    eax, eax
0x100411884  jns     short loc_1004118A2
0x100411886  lea     rdx, aSqlFederation; "SQL federation"
0x10041188d  mov     ecx, 42F2h; unsigned int
0x100411892  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100411897  mov     ecx, 2Bh ; '+'
0x10041189c  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x1004118a2  lea     rcx, aFederationInit; "Federation Initialization Completed Suc"...
0x1004118a9  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x1004118ae  mov     rbx, [rsp+38h+arg_8]
0x1004118b3  add     rsp, 30h
0x1004118b7  pop     rsi
0x1004118b8  retn
```
