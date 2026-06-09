# TraceLoggingWriteRemediationState(CThirdPartyManager *,RemediationAction,long,int *,ushort const *)

- ea: `0x18003b3cc`
- end: `0x18003b4f1`
- name: `?TraceLoggingWriteRemediationState@@YAXPEAVCThirdPartyManager@@W4RemediationAction@@JPEAHPEBG@Z`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003c5ec`

## callees

- `0x18000190c`
- `0x18000a490`
- `0x18001c690`
- `0x180023dec`
- `0x18003b3cc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003b437`
- `msvcrt!_wcsicmp` at `0x18003b437`

## pseudocode

```c
int __fastcall TraceLoggingWriteRemediationState(
        CThirdPartyManager *a1,
        unsigned int a2,
        int a3,
        unsigned int *a4,
        wchar_t *String2)
{
  int result; // eax
  unsigned int v10; // ebx
  struct CExternalBase *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15[2]; // [rsp+50h] [rbp-30h] BYREF
  struct CExternalBase *v16; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-20h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h] BYREF
  __int64 v19; // [rsp+70h] [rbp-10h] BYREF

  v15[0] = 0;
  result = CThirdPartyManager::GetNumberOfProducts(a1, v15);
  if ( result >= 0 )
  {
    v10 = 0;
    v16 = 0;
    if ( v15[0] )
    {
      while ( 1 )
      {
        result = CThirdPartyManager::GetProductAtOffset(a1, v10, &v16);
        if ( result >= 0 )
        {
          v11 = v16;
          result = _wcsicmp(*((const wchar_t **)v16 + 1), String2);
          if ( !result )
            break;
        }
        if ( ++v10 >= v15[0] )
          return result;
      }
      result = dword_180053218;
      if ( (unsigned int)dword_180053218 > 5 )
      {
        result = tlgKeywordOn(&dword_180053218, 0x400000000000LL);
        if ( (_BYTE)result )
        {
          v15[0] = *a4;
          v15[1] = a2;
          LODWORD(v16) = a3;
          v17 = *((_QWORD *)v11 + 6);
          v18 = *((_QWORD *)v11 + 2);
          v19 = *((_QWORD *)v11 + 5);
          return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                   v12,
                   (__int64)&dword_18004C6D4,
                   v13,
                   v14,
                   &v19,
                   &v18,
                   &v17);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003b3cc  push    rbp
0x18003b3ce  push    rbx
0x18003b3cf  push    rsi
0x18003b3d0  push    r12
0x18003b3d2  push    r13
0x18003b3d4  push    r14
0x18003b3d6  push    r15
0x18003b3d8  mov     rbp, rsp
0x18003b3db  sub     rsp, 80h
0x18003b3e2  mov     r13d, edx
0x18003b3e5  mov     [rbp+var_30], 0
0x18003b3ec  lea     rdx, [rbp+var_30]; unsigned int *
0x18003b3f0  mov     r15, r9
0x18003b3f3  mov     r12d, r8d
0x18003b3f6  mov     r14, rcx
0x18003b3f9  call    ?GetNumberOfProducts@CThirdPartyManager@@QEAAJAEAK@Z; CThirdPartyManager::GetNumberOfProducts(ulong &)
0x18003b3fe  test    eax, eax
0x18003b400  js      loc_18003B4DE
0x18003b406  xor     ebx, ebx
0x18003b408  mov     [rbp+var_28], 0
0x18003b410  cmp     [rbp+var_30], ebx
0x18003b413  jbe     loc_18003B4DE
0x18003b419  lea     r8, [rbp+var_28]; struct CExternalBase **
0x18003b41d  mov     edx, ebx; unsigned int
0x18003b41f  mov     rcx, r14; this
0x18003b422  call    ?GetProductAtOffset@CThirdPartyManager@@QEAAJKPEAPEAVCExternalBase@@@Z; CThirdPartyManager::GetProductAtOffset(ulong,CExternalBase * *)
0x18003b427  test    eax, eax
0x18003b429  js      short loc_18003B441
0x18003b42b  mov     rsi, [rbp+var_28]
0x18003b42f  mov     rdx, [rbp+String2]; String2
0x18003b433  mov     rcx, [rsi+8]; String1
0x18003b437  call    cs:__imp__wcsicmp
0x18003b43d  test    eax, eax
0x18003b43f  jz      short loc_18003B44D
0x18003b441  inc     ebx
0x18003b443  cmp     ebx, [rbp+var_30]
0x18003b446  jb      short loc_18003B419
0x18003b448  jmp     loc_18003B4DE
0x18003b44d  mov     eax, cs:dword_180053218
0x18003b453  cmp     eax, 5
0x18003b456  jbe     loc_18003B4DE
0x18003b45c  mov     rdx, 400000000000h
0x18003b466  lea     rcx, dword_180053218
0x18003b46d  call    _tlgKeywordOn
0x18003b472  test    al, al
0x18003b474  jz      short loc_18003B4DE
0x18003b476  mov     eax, [r15]
0x18003b479  lea     rdx, dword_18004C6D4
0x18003b480  mov     [rbp+var_30], eax
0x18003b483  mov     [rbp+var_2C], r13d
0x18003b487  mov     dword ptr [rbp+var_28], r12d
0x18003b48b  mov     rax, [rsi+30h]
0x18003b48f  mov     [rbp+var_20], rax
0x18003b493  mov     rax, [rsi+10h]
0x18003b497  mov     [rbp+var_18], rax
0x18003b49b  mov     rax, [rsi+28h]
0x18003b49f  mov     [rbp+var_10], rax
0x18003b4a3  lea     rax, [rbp+var_30]
0x18003b4a7  mov     [rsp+80h+var_38], rax
0x18003b4ac  lea     rax, [rbp+var_2C]
0x18003b4b0  mov     [rsp+80h+var_40], rax
0x18003b4b5  lea     rax, [rbp+var_28]
0x18003b4b9  mov     [rsp+80h+var_48], rax
0x18003b4be  lea     rax, [rbp+var_20]
0x18003b4c2  mov     [rsp+80h+var_50], rax
0x18003b4c7  lea     rax, [rbp+var_18]
0x18003b4cb  mov     [rsp+80h+var_58], rax
0x18003b4d0  lea     rax, [rbp+var_10]
0x18003b4d4  mov     [rsp+80h+var_60], rax
0x18003b4d9  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b4de  add     rsp, 80h
0x18003b4e5  pop     r15
0x18003b4e7  pop     r14
0x18003b4e9  pop     r13
0x18003b4eb  pop     r12
0x18003b4ed  pop     rsi
0x18003b4ee  pop     rbx
0x18003b4ef  pop     rbp
0x18003b4f0  retn
```
