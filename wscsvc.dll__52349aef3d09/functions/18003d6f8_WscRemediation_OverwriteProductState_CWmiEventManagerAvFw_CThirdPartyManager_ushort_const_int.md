# WscRemediation_OverwriteProductState(CWmiEventManagerAvFw *,CThirdPartyManager *,ushort const *,int)

- ea: `0x18003d6f8`
- end: `0x18003d85c`
- name: `?WscRemediation_OverwriteProductState@@YAHPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@PEBGH@Z`
- size: `356`
- prototype: `__int64 __fastcall(struct CWmiEventManagerAvFw *this, struct CThirdPartyManager *, wchar_t *String2, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18003c5ec`

## callees

- `0x180008cc0`
- `0x18000a490`
- `0x18001c690`
- `0x1800202e8`
- `0x18003d364`
- `0x18003d6f8`
- `0x18003dd70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003d7a4`
- `msvcrt!_wcsicmp` at `0x18003d7a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d818`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d818`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d758`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d758`

## pseudocode

```c
__int64 __fastcall WscRemediation_OverwriteProductState(
        struct CWmiEventManagerAvFw *this,
        struct CThirdPartyManager *a2,
        wchar_t *String2)
{
  unsigned int v3; // edi
  unsigned int i; // ebx
  struct CExternalBase *v8; // rsi
  __int64 v9; // r8
  const wchar_t *v10; // rax
  struct CExternalBase *v12; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v13; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v13 = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 16));
  if ( (int)CThirdPartyManager::GetNumberOfProducts(a2, &v13) >= 0 )
  {
    for ( i = 0; i < v13 && (int)CThirdPartyManager::GetProductAtOffset(a2, i, &v12) >= 0; ++i )
    {
      v8 = v12;
      if ( !_wcsicmp(*((const wchar_t **)v12 + 1), String2) )
      {
        v3 = CExternalBase::SetProductState(v8, 0, v9);
        WscDSA_UpdateStore(this, v8, 0);
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v10 = L"changed to ";
          if ( !v3 )
            v10 = L"stayed ";
          WPP_SF_SSS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)L"ProductState_Off",
            (_DWORD)String2,
            (__int64)v10,
            (__int64)L"ProductState_Off");
        }
        break;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 16));
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x18003d6f8  mov     rax, rsp
0x18003d6fb  mov     [rax+8], rbx
0x18003d6ff  mov     [rax+20h], r9d
0x18003d703  push    rbp
0x18003d704  push    rsi
0x18003d705  push    rdi
0x18003d706  push    r12
0x18003d708  push    r13
0x18003d70a  push    r14
0x18003d70c  push    r15
0x18003d70e  sub     rsp, 30h
0x18003d712  xor     edi, edi
0x18003d714  mov     dword ptr [rax+20h], 0
0x18003d71b  mov     [rax+10h], rdi
0x18003d71f  mov     r15, r8
0x18003d722  mov     rbp, rdx
0x18003d725  mov     r12, rcx
0x18003d728  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d72f  lea     r13, WPP_GLOBAL_Control
0x18003d736  cmp     rcx, r13
0x18003d739  jz      short loc_18003D754
0x18003d73b  test    byte ptr [rcx+1Ch], 8
0x18003d73f  jz      short loc_18003D754
0x18003d741  mov     rcx, [rcx+10h]
0x18003d745  lea     edx, [rdi+28h]
0x18003d748  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d74f  call    WPP_SF_
0x18003d754  lea     rcx, [rbp+10h]; lpCriticalSection
0x18003d758  call    cs:__imp_EnterCriticalSection
0x18003d75e  lea     rdx, [rsp+68h+arg_18]; unsigned int *
0x18003d766  mov     rcx, rbp; this
0x18003d769  call    ?GetNumberOfProducts@CThirdPartyManager@@QEAAJAEAK@Z; CThirdPartyManager::GetNumberOfProducts(ulong &)
0x18003d76e  test    eax, eax
0x18003d770  js      loc_18003D814
0x18003d776  xor     ebx, ebx
0x18003d778  cmp     ebx, [rsp+68h+arg_18]
0x18003d77f  jnb     loc_18003D814
0x18003d785  lea     r8, [rsp+68h+arg_8]; struct CExternalBase **
0x18003d78a  mov     edx, ebx; unsigned int
0x18003d78c  mov     rcx, rbp; this
0x18003d78f  call    ?GetProductAtOffset@CThirdPartyManager@@QEAAJKPEAPEAVCExternalBase@@@Z; CThirdPartyManager::GetProductAtOffset(ulong,CExternalBase * *)
0x18003d794  test    eax, eax
0x18003d796  js      short loc_18003D814
0x18003d798  mov     rsi, [rsp+68h+arg_8]
0x18003d79d  mov     rdx, r15; String2
0x18003d7a0  mov     rcx, [rsi+8]; String1
0x18003d7a4  call    cs:__imp__wcsicmp
0x18003d7aa  test    eax, eax
0x18003d7ac  jz      short loc_18003D7B2
0x18003d7ae  inc     ebx
0x18003d7b0  jmp     short loc_18003D778
0x18003d7b2  xor     edx, edx
0x18003d7b4  mov     rcx, rsi
0x18003d7b7  call    ?SetProductState@CExternalBase@@QEAAHW4ProductState@@@Z; CExternalBase::SetProductState(ProductState)
0x18003d7bc  xor     r8d, r8d; struct CExternalBase *
0x18003d7bf  mov     rdx, rsi; struct CExternalBase *
0x18003d7c2  mov     rcx, r12; this
0x18003d7c5  mov     edi, eax
0x18003d7c7  call    ?WscDSA_UpdateStore@@YAJPEAVCWmiEventManagerAvFw@@PEAVCExternalBase@@1@Z; WscDSA_UpdateStore(CWmiEventManagerAvFw *,CExternalBase *,CExternalBase *)
0x18003d7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d7d3  cmp     rcx, r13
0x18003d7d6  jz      short loc_18003D814
0x18003d7d8  test    byte ptr [rcx+1Ch], 4
0x18003d7dc  jz      short loc_18003D814
0x18003d7de  mov     rcx, [rcx+10h]
0x18003d7e2  lea     rdx, aStayed; "stayed "
0x18003d7e9  test    edi, edi
0x18003d7eb  lea     r8, aProductstateOf; "ProductState_Off"
0x18003d7f2  mov     [rsp+68h+var_40], r8
0x18003d7f7  lea     rax, aChangedTo; "changed to "
0x18003d7fe  cmovz   rax, rdx
0x18003d802  mov     r9, r15
0x18003d805  mov     edx, 29h ; ')'
0x18003d80a  mov     [rsp+68h+var_48], rax
0x18003d80f  call    WPP_SF_SSS
0x18003d814  lea     rcx, [rbp+10h]; lpCriticalSection
0x18003d818  call    cs:__imp_LeaveCriticalSection
0x18003d81e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d825  cmp     rcx, r13
0x18003d828  jz      short loc_18003D845
0x18003d82a  test    byte ptr [rcx+1Ch], 8
0x18003d82e  jz      short loc_18003D845
0x18003d830  mov     rcx, [rcx+10h]
0x18003d834  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d83b  mov     edx, 2Ah ; '*'
0x18003d840  call    WPP_SF_
0x18003d845  mov     rbx, [rsp+68h+arg_0]
0x18003d84a  mov     eax, edi
0x18003d84c  add     rsp, 30h
0x18003d850  pop     r15
0x18003d852  pop     r14
0x18003d854  pop     r13
0x18003d856  pop     r12
0x18003d858  pop     rdi
0x18003d859  pop     rsi
0x18003d85a  pop     rbp
0x18003d85b  retn
```
