# DllRegisterServer

- ea: `0x18000a3c0`
- end: `0x18000a4fa`
- name: `DllRegisterServer`
- size: `314`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003ce0`
- `0x180007c30`
- `0x18000a3c0`
- `0x18000d348`
- `0x18000d43c`
- `0x180016010`

## string_xrefs

- `0x18000a401`: `DllRegisterServer`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  __int64 *v4; // rbx
  int v5; // ecx
  __int64 *v6; // rax
  __int64 v7; // rdi
  int v8; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v9; // rax
  HRESULT v10; // ebx
  _DWORD v12[18]; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_dc1e325698af3ebf27dfb8b3dda856da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v12, "DllRegisterServer", 96);
  v2 = qword_18001DA18;
  if ( qword_18001DA18 )
  {
    while ( *(_QWORD *)v2 )
    {
      if ( (*(int (__fastcall **)(__int64))(v2 + 8))(1) < 0 )
        goto LABEL_19;
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v2 + 56))();
      if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v2, v3, 1) < 0 )
        goto LABEL_19;
      v2 += 72;
    }
  }
  v4 = off_18001D120[0];
  v5 = 0;
  v6 = off_18001D128;
  if ( off_18001D120[0] >= off_18001D128 )
  {
LABEL_17:
    if ( ATL::_pPerfRegFunc )
      ATL::_pPerfRegFunc(hInstance);
    goto LABEL_19;
  }
  while ( 1 )
  {
    v7 = *v4;
    if ( *v4 )
      break;
LABEL_15:
    if ( ++v4 >= v6 )
      goto LABEL_16;
  }
  v8 = (*(__int64 (__fastcall **)(__int64))(v7 + 8))(1);
  v5 = v8;
  if ( v8 >= 0 )
  {
    v9 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (__fastcall **)(_QWORD))(v7 + 56))((unsigned int)v8);
    v5 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v9, 1);
    if ( v5 >= 0 )
    {
      v6 = off_18001D128;
      goto LABEL_15;
    }
  }
LABEL_16:
  if ( v5 >= 0 )
    goto LABEL_17;
LABEL_19:
  v10 = v12[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v12, v0, v1);
  return v10;
}

```

## disassembly

```asm
0x18000a3c0  mov     [rsp+arg_0], rbx
0x18000a3c5  push    rdi
0x18000a3c6  sub     rsp, 60h
0x18000a3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3d1  lea     rax, WPP_GLOBAL_Control
0x18000a3d8  cmp     rcx, rax
0x18000a3db  jz      short loc_18000A3FB
0x18000a3dd  test    dword ptr [rcx+1Ch], 20000000h
0x18000a3e4  jz      short loc_18000A3FB
0x18000a3e6  mov     rcx, [rcx+10h]
0x18000a3ea  lea     r8, WPP_dc1e325698af3ebf27dfb8b3dda856da_Traceguids
0x18000a3f1  mov     edx, 0Bh
0x18000a3f6  call    WPP_SF_
0x18000a3fb  mov     r8d, 60h ; '`'; unsigned __int16
0x18000a401  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x18000a408  lea     rcx, [rsp+68h+var_48]; this
0x18000a40d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000a412  mov     rbx, cs:qword_18001DA18
0x18000a419  test    rbx, rbx
0x18000a41c  jz      short loc_18000A462
0x18000a41e  jmp     short loc_18000A45C
0x18000a420  mov     rax, [rbx+8]
0x18000a424  mov     ecx, 1
0x18000a429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42e  test    eax, eax
0x18000a430  js      loc_18000A4DF
0x18000a436  mov     rax, [rbx+38h]
0x18000a43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a43f  mov     rcx, [rbx]; rguid
0x18000a442  mov     r8d, 1; int
0x18000a448  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000a44b  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000a450  test    eax, eax
0x18000a452  js      loc_18000A4DF
0x18000a458  add     rbx, 48h ; 'H'
0x18000a45c  cmp     qword ptr [rbx], 0
0x18000a460  jnz     short loc_18000A420
0x18000a462  mov     rbx, cs:off_18001D120
0x18000a469  xor     ecx, ecx
0x18000a46b  mov     rax, cs:off_18001D128
0x18000a472  cmp     rbx, rax
0x18000a475  jnb     short loc_18000A4C7
0x18000a477  mov     rdi, [rbx]
0x18000a47a  test    rdi, rdi
0x18000a47d  jz      short loc_18000A4BA
0x18000a47f  mov     rax, [rdi+8]
0x18000a483  mov     ecx, 1
0x18000a488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48d  mov     ecx, eax
0x18000a48f  test    eax, eax
0x18000a491  js      short loc_18000A4C3
0x18000a493  mov     rax, [rdi+38h]
0x18000a497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a49c  mov     rcx, [rdi]; rguid
0x18000a49f  mov     r8d, 1; int
0x18000a4a5  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000a4a8  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000a4ad  mov     ecx, eax
0x18000a4af  test    eax, eax
0x18000a4b1  js      short loc_18000A4C3
0x18000a4b3  mov     rax, cs:off_18001D128
0x18000a4ba  add     rbx, 8
0x18000a4be  cmp     rbx, rax
0x18000a4c1  jb      short loc_18000A477
0x18000a4c3  test    ecx, ecx
0x18000a4c5  js      short loc_18000A4DF
0x18000a4c7  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000a4ce  test    rax, rax
0x18000a4d1  jz      short loc_18000A4DF
0x18000a4d3  mov     rcx, cs:hInstance
0x18000a4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4df  mov     ebx, [rsp+68h+var_48]
0x18000a4e3  lea     rcx, [rsp+68h+var_48]; this
0x18000a4e8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000a4ed  mov     eax, ebx
0x18000a4ef  mov     rbx, [rsp+68h+arg_0]
0x18000a4f4  add     rsp, 60h
0x18000a4f8  pop     rdi
0x18000a4f9  retn
```
