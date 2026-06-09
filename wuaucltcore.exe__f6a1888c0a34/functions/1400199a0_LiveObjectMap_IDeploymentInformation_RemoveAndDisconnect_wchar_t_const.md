# LiveObjectMap<IDeploymentInformation *>::RemoveAndDisconnect(wchar_t const *)

- ea: `0x1400199a0`
- end: `0x140019a7e`
- name: `?RemoveAndDisconnect@?$LiveObjectMap@PEAUIDeploymentInformation@@@@QEAAJPEB_W@Z`
- size: `222`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400195a0`
- `0x1400196b0`

## callees

- `0x14000b1f4`
- `0x14000d4cc`
- `0x1400199a0`
- `0x140019ddc`
- `0x140019f64`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x140019a19`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x140019a19`

## pseudocode

```c
__int64 __fastcall LiveObjectMap<IDeploymentInformation *>::RemoveAndDisconnect(__int64 a1, __int64 a2)
{
  unsigned int IndexOf; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __m128i v6; // xmm6
  void *v7; // rcx
  HRESULT v8; // eax
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = a2;
  IndexOf = CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::GetIndexOf(
              a1,
              &v12);
  v4 = 0;
  if ( IndexOf >= *(_DWORD *)(a1 + 20) )
  {
    v4 = -2145124345;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInform"
                    "ationFactory.cpp",
      (const char *)0x80240007LL,
      v10);
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 8);
    v6 = *(__m128i *)(v5 + 16LL * IndexOf);
    *(_OWORD *)(v5 + 16LL * IndexOf) = 0;
    CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
      a1,
      IndexOf,
      IndexOf,
      0);
    v7 = (void *)_mm_srli_si128(v6, 8).m128i_u64[0];
    if ( v7 )
      SusFree(v7);
    if ( v6.m128i_i64[0] )
    {
      v8 = CoDisconnectObject((LPUNKNOWN)v6.m128i_i64[0], 0);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x19,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentIn"
                        "formationFactory.cpp",
          (const char *)(unsigned int)v8,
          v10);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6.m128i_i64[0] + 16LL))(v6.m128i_i64[0]);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400199a0  mov     rax, rsp
0x1400199a3  mov     [rax+10h], rbx
0x1400199a7  push    rdi
0x1400199a8  sub     rsp, 30h
0x1400199ac  mov     [rax+8], rdx
0x1400199b0  mov     rdi, rcx
0x1400199b3  lea     rdx, [rax+8]
0x1400199b7  movaps  xmmword ptr [rax-18h], xmm6
0x1400199bb  call    ?GetIndexOf@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::GetIndexOf(wchar_t * const &)
0x1400199c0  xor     ebx, ebx
0x1400199c2  cmp     eax, [rdi+14h]
0x1400199c5  jnb     loc_140019A4D
0x1400199cb  mov     rdx, [rdi+8]
0x1400199cf  xorps   xmm0, xmm0
0x1400199d2  mov     r8d, eax
0x1400199d5  xor     r9d, r9d
0x1400199d8  add     r8, r8
0x1400199db  mov     rcx, rdi
0x1400199de  movups  xmm6, xmmword ptr [rdx+r8*8]
0x1400199e3  movups  xmmword ptr [rdx+r8*8], xmm0
0x1400199e8  mov     r8d, eax
0x1400199eb  mov     edx, eax
0x1400199ed  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x1400199f2  movdqa  xmm0, xmm6
0x1400199f6  psrldq  xmm0, 8
0x1400199fb  movq    rcx, xmm0; lpMem
0x140019a00  test    rcx, rcx
0x140019a03  jz      short loc_140019A0A
0x140019a05  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140019a0a  movq    rdi, xmm6
0x140019a0f  test    rdi, rdi
0x140019a12  jz      short loc_140019A6C
0x140019a14  xor     edx, edx; dwReserved
0x140019a16  mov     rcx, rdi; pUnk
0x140019a19  call    cs:__imp_CoDisconnectObject
0x140019a1f  test    eax, eax
0x140019a21  jns     short loc_140019A3C
0x140019a23  mov     rcx, [rsp+38h]; this
0x140019a28  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140019a2f  mov     r9d, eax; char *
0x140019a32  mov     edx, 19h; void *
0x140019a37  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140019a3c  mov     rax, [rdi]
0x140019a3f  mov     rcx, rdi
0x140019a42  mov     rax, [rax+10h]
0x140019a46  call    _guard_dispatch_icall
0x140019a4b  jmp     short loc_140019A6C
0x140019a4d  mov     rcx, [rsp+38h]; this
0x140019a52  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140019a59  mov     r9d, 80240007h; char *
0x140019a5f  mov     edx, 17h; void *
0x140019a64  mov     ebx, r9d
0x140019a67  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140019a6c  movaps  xmm6, xmmword ptr [rsp+38h+var_18]
0x140019a71  mov     eax, ebx
0x140019a73  mov     rbx, [rsp+38h+arg_8]
0x140019a78  add     rsp, 30h
0x140019a7c  pop     rdi
0x140019a7d  retn
```
