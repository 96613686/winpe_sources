# DllUnregisterServer

- ea: `0x18000a500`
- end: `0x18000a616`
- name: `DllUnregisterServer`
- size: `278`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003ce0`
- `0x180007c30`
- `0x18000a500`
- `0x18000d348`
- `0x18000d43c`
- `0x180016010`

## string_xrefs

- `0x18000a541`: `DllUnregisterServer`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  __int64 *v4; // rbx
  __int64 *v5; // rax
  __int64 v6; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  _BYTE v9[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_dc1e325698af3ebf27dfb8b3dda856da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v9, "DllUnregisterServer", 120);
  v2 = qword_18001DA18;
  if ( qword_18001DA18 )
  {
    while ( *(_QWORD *)v2 )
    {
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v2 + 56))();
      if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v2, v3, 0) < 0
        || (*(int (__fastcall **)(_QWORD))(v2 + 8))(0) < 0 )
      {
        goto LABEL_19;
      }
      v2 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || ATL::_pPerfUnRegFunc() >= 0 )
  {
    v4 = off_18001D120[0];
    v5 = off_18001D128;
    while ( v4 < v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v6 + 56))();
        if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 0) < 0
          || (*(int (__fastcall **)(_QWORD))(v6 + 8))(0) < 0 )
        {
          break;
        }
        v5 = off_18001D128;
      }
      ++v4;
    }
  }
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v9, v0, v1);
  return 0;
}

```

## disassembly

```asm
0x18000a500  mov     [rsp+arg_0], rbx
0x18000a505  push    rdi
0x18000a506  sub     rsp, 60h
0x18000a50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a511  lea     rax, WPP_GLOBAL_Control
0x18000a518  cmp     rcx, rax
0x18000a51b  jz      short loc_18000A53B
0x18000a51d  test    dword ptr [rcx+1Ch], 20000000h
0x18000a524  jz      short loc_18000A53B
0x18000a526  mov     rcx, [rcx+10h]
0x18000a52a  lea     r8, WPP_dc1e325698af3ebf27dfb8b3dda856da_Traceguids
0x18000a531  mov     edx, 0Ch
0x18000a536  call    WPP_SF_
0x18000a53b  mov     r8d, 78h ; 'x'; unsigned __int16
0x18000a541  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x18000a548  lea     rcx, [rsp+68h+var_48]; this
0x18000a54d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000a552  mov     rbx, cs:qword_18001DA18
0x18000a559  test    rbx, rbx
0x18000a55c  jz      short loc_18000A598
0x18000a55e  jmp     short loc_18000A592
0x18000a560  mov     rax, [rbx+38h]
0x18000a564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a569  mov     rcx, [rbx]; rguid
0x18000a56c  xor     r8d, r8d; int
0x18000a56f  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000a572  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000a577  test    eax, eax
0x18000a579  js      loc_18000A5FF
0x18000a57f  mov     rax, [rbx+8]
0x18000a583  xor     ecx, ecx
0x18000a585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a58a  test    eax, eax
0x18000a58c  js      short loc_18000A5FF
0x18000a58e  add     rbx, 48h ; 'H'
0x18000a592  cmp     qword ptr [rbx], 0
0x18000a596  jnz     short loc_18000A560
0x18000a598  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000a59f  test    rax, rax
0x18000a5a2  jz      short loc_18000A5AD
0x18000a5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a9  test    eax, eax
0x18000a5ab  js      short loc_18000A5FF
0x18000a5ad  mov     rbx, cs:off_18001D120
0x18000a5b4  mov     rax, cs:off_18001D128
0x18000a5bb  jmp     short loc_18000A5FA
0x18000a5bd  mov     rdi, [rbx]
0x18000a5c0  test    rdi, rdi
0x18000a5c3  jz      short loc_18000A5F6
0x18000a5c5  mov     rax, [rdi+38h]
0x18000a5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ce  mov     rcx, [rdi]; rguid
0x18000a5d1  xor     r8d, r8d; int
0x18000a5d4  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000a5d7  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000a5dc  test    eax, eax
0x18000a5de  js      short loc_18000A5FF
0x18000a5e0  mov     rax, [rdi+8]
0x18000a5e4  xor     ecx, ecx
0x18000a5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5eb  test    eax, eax
0x18000a5ed  js      short loc_18000A5FF
0x18000a5ef  mov     rax, cs:off_18001D128
0x18000a5f6  add     rbx, 8
0x18000a5fa  cmp     rbx, rax
0x18000a5fd  jb      short loc_18000A5BD
0x18000a5ff  lea     rcx, [rsp+68h+var_48]; this
0x18000a604  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000a609  mov     rbx, [rsp+68h+arg_0]
0x18000a60e  xor     eax, eax
0x18000a610  add     rsp, 60h
0x18000a614  pop     rdi
0x18000a615  retn
```
