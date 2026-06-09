# CSqmCommonDataPointManager::AddCommonDatapoints(HSQMSESSION__ *)

- ea: `0x180041b04`
- end: `0x180041d2e`
- name: `?AddCommonDatapoints@CSqmCommonDataPointManager@@QEAAJPEAUHSQMSESSION__@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(CSqmCommonDataPointManager *__hidden this, struct HSQMSESSION__ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f24`

## callees

- `0x180003f30`
- `0x180014b78`
- `0x180041b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ce5`
- `SQMAPI!SqmAddToStreamString` at `0x180041c99`
- `SQMAPI!SqmAddToStreamString` at `0x180041c99`
- `SQMAPI!SqmAddToStreamDWord` at `0x180041cae`
- `SQMAPI!SqmAddToStreamDWord` at `0x180041cae`
- `SQMAPI!SqmAddToStreamDWord64` at `0x180041c84`
- `SQMAPI!SqmAddToStreamDWord64` at `0x180041c84`
- `SQMAPI!SqmSet` at `0x180041b67`
- `SQMAPI!SqmSet` at `0x180041b67`
- `SQMAPI!SqmSetDWord64` at `0x180041ba4`
- `SQMAPI!SqmSetDWord64` at `0x180041ba4`
- `SQMAPI!SqmSetString` at `0x180041be2`
- `SQMAPI!SqmSetString` at `0x180041be2`

## string_xrefs

- `0x180041b4a`: `GetStaticCommonDatapointsFromRegistry() failed`
- `0x180041b7a`: `SqmSet failed to Set Common Datapoint with DataPointID, %d, hr=0x%d!`
- `0x180041bb7`: `SqmSetDWord64 failed to Set Common Datapoint, with DataPointId:%d, hr=0x%d!`
- `0x180041bf5`: `SqmSetString failed to Set Common Datapoint ID, %d, hr=0x%d!`
- `0x180041cfd`: `Invalid Stream Cache Entry for Datapint Id %d`

## pseudocode

```c
__int64 __fastcall CSqmCommonDataPointManager::AddCommonDatapoints(unsigned int **this, struct HSQMSESSION__ *a2)
{
  struct HSQMSESSION__ *v2; // r15
  DWORD StaticCommonDatapointsFromRegistry; // edi
  unsigned int *i; // rbx
  unsigned int *j; // rbx
  unsigned int *k; // rbx
  unsigned int *m; // rbx
  __int64 v9; // rbp
  signed __int64 v10; // r14
  signed __int64 v11; // r12
  unsigned int n; // r13d
  int v13; // eax
  DWORD LastError; // eax
  const char *v15; // rdx

  v2 = CSQMUtil::m_hSQMSession;
  if ( CSQMUtil::m_hSQMSession )
  {
    StaticCommonDatapointsFromRegistry = CSqmCommonDataPointManager::GetStaticCommonDatapointsFromRegistry((CSqmCommonDataPointManager *)this);
    if ( StaticCommonDatapointsFromRegistry )
    {
      _DbgPrintMessage(8, "GetStaticCommonDatapointsFromRegistry() failed");
    }
    else
    {
      for ( i = this[1]; i; i = (unsigned int *)*((_QWORD *)i + 1) )
      {
        if ( !(unsigned int)SqmSet(v2, *i, i[1]) )
        {
          StaticCommonDatapointsFromRegistry = GetLastError();
          _DbgPrintMessage(
            8,
            "SqmSet failed to Set Common Datapoint with DataPointID, %d, hr=0x%d!",
            *i,
            StaticCommonDatapointsFromRegistry);
        }
      }
      for ( j = *this; j; j = (unsigned int *)*((_QWORD *)j + 2) )
      {
        if ( !(unsigned int)SqmSetDWord64(v2, *j, *((_QWORD *)j + 1)) )
        {
          StaticCommonDatapointsFromRegistry = GetLastError();
          _DbgPrintMessage(
            8,
            "SqmSetDWord64 failed to Set Common Datapoint, with DataPointId:%d, hr=0x%d!",
            *j,
            StaticCommonDatapointsFromRegistry);
        }
      }
      for ( k = this[2]; k; k = (unsigned int *)*((_QWORD *)k + 33) )
      {
        if ( !(unsigned int)SqmSetString(v2, *k, k + 1) )
        {
          StaticCommonDatapointsFromRegistry = GetLastError();
          _DbgPrintMessage(
            8,
            "SqmSetString failed to Set Common Datapoint ID, %d, hr=0x%d!",
            *k,
            StaticCommonDatapointsFromRegistry);
        }
      }
      for ( m = this[3]; m; m = (unsigned int *)*((_QWORD *)m + 2) )
      {
        v9 = *((_QWORD *)m + 1);
        if ( v9 && m[1] > 0xC )
        {
          v10 = v9 + 12;
          v11 = v9 + m[1];
          for ( n = 0; ; ++n )
          {
            if ( n >= *(_DWORD *)(v9 + 8) )
              goto LABEL_41;
            if ( v10 > v11 || v10 + *(unsigned int *)(v10 + 4) > v11 )
              break;
            switch ( *(_DWORD *)v10 )
            {
              case 1:
                v13 = SqmAddToStreamDWord(v2, *m, *(unsigned int *)(v9 + 4));
                break;
              case 2:
                v13 = SqmAddToStreamString(v2, *m, *(unsigned int *)(v9 + 4), v10 + 8);
                break;
              case 3:
                v13 = SqmAddToStreamDWord64(v2, *m, *(unsigned int *)(v9 + 4), *(_QWORD *)(v10 + 8));
                break;
              default:
                LastError = GetLastError();
                v15 = "Invalid data detected in stream entry for Datapoint %d, hr=0x%d!";
LABEL_37:
                StaticCommonDatapointsFromRegistry = LastError;
                _DbgPrintMessage(8, v15, *m, LastError);
                goto LABEL_41;
            }
            if ( !v13 )
            {
              LastError = GetLastError();
              v15 = "AddToStream call failed for Datapoint %d, hr=0x%d!";
              goto LABEL_37;
            }
            v10 += *(unsigned int *)(v10 + 4);
          }
          _DbgPrintMessage(8, "Invalid Stream Entry for Datapoint Id %d", *m);
        }
        else
        {
          _DbgPrintMessage(8, "Invalid Stream Cache Entry for Datapint Id %d", *m);
        }
LABEL_41:
        ;
      }
    }
  }
  else
  {
    StaticCommonDatapointsFromRegistry = -2147024809;
    _DbgPrintMessage(8, "Invalid Session, pSqmSession");
  }
  return StaticCommonDatapointsFromRegistry;
}

```

## disassembly

```asm
0x180041b04  push    rbx
0x180041b06  push    rbp
0x180041b07  push    rsi
0x180041b08  push    rdi
0x180041b09  push    r12
0x180041b0b  push    r13
0x180041b0d  push    r14
0x180041b0f  push    r15
0x180041b11  sub     rsp, 28h
0x180041b15  mov     r15, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x180041b1c  mov     r14, rcx
0x180041b1f  test    r15, r15
0x180041b22  jnz     short loc_180041B3F
0x180041b24  mov     edi, 80070057h
0x180041b29  lea     rdx, aInvalidSession; "Invalid Session, pSqmSession"
0x180041b30  mov     ecx, 8; int
0x180041b35  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041b3a  jmp     loc_180041D1B
0x180041b3f  call    ?GetStaticCommonDatapointsFromRegistry@CSqmCommonDataPointManager@@QEAAJXZ; CSqmCommonDataPointManager::GetStaticCommonDatapointsFromRegistry(void)
0x180041b44  mov     edi, eax
0x180041b46  test    eax, eax
0x180041b48  jz      short loc_180041B53
0x180041b4a  lea     rdx, aGetstaticcommo; "GetStaticCommonDatapointsFromRegistry()"...
0x180041b51  jmp     short loc_180041B30
0x180041b53  mov     rbx, [r14+8]
0x180041b57  mov     esi, 8
0x180041b5c  jmp     short loc_180041B91
0x180041b5e  mov     r8d, [rbx+4]
0x180041b62  mov     rcx, r15
0x180041b65  mov     edx, [rbx]
0x180041b67  call    cs:__imp_SqmSet
0x180041b6d  test    eax, eax
0x180041b6f  jnz     short loc_180041B8D
0x180041b71  call    cs:__imp_GetLastError
0x180041b77  mov     r8d, [rbx]
0x180041b7a  lea     rdx, aSqmsetFailedTo; "SqmSet failed to Set Common Datapoint w"...
0x180041b81  mov     r9d, eax
0x180041b84  mov     ecx, esi; int
0x180041b86  mov     edi, eax
0x180041b88  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041b8d  mov     rbx, [rbx+8]
0x180041b91  test    rbx, rbx
0x180041b94  jnz     short loc_180041B5E
0x180041b96  mov     rbx, [r14]
0x180041b99  jmp     short loc_180041BCE
0x180041b9b  mov     r8, [rbx+8]
0x180041b9f  mov     rcx, r15
0x180041ba2  mov     edx, [rbx]
0x180041ba4  call    cs:__imp_SqmSetDWord64
0x180041baa  test    eax, eax
0x180041bac  jnz     short loc_180041BCA
0x180041bae  call    cs:__imp_GetLastError
0x180041bb4  mov     r8d, [rbx]
0x180041bb7  lea     rdx, aSqmsetdword64F; "SqmSetDWord64 failed to Set Common Data"...
0x180041bbe  mov     r9d, eax
0x180041bc1  mov     ecx, esi; int
0x180041bc3  mov     edi, eax
0x180041bc5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041bca  mov     rbx, [rbx+10h]
0x180041bce  test    rbx, rbx
0x180041bd1  jnz     short loc_180041B9B
0x180041bd3  mov     rbx, [r14+10h]
0x180041bd7  jmp     short loc_180041C0F
0x180041bd9  mov     edx, [rbx]
0x180041bdb  lea     r8, [rbx+4]
0x180041bdf  mov     rcx, r15
0x180041be2  call    cs:__imp_SqmSetString
0x180041be8  test    eax, eax
0x180041bea  jnz     short loc_180041C08
0x180041bec  call    cs:__imp_GetLastError
0x180041bf2  mov     r8d, [rbx]
0x180041bf5  lea     rdx, aSqmsetstringFa; "SqmSetString failed to Set Common Datap"...
0x180041bfc  mov     r9d, eax
0x180041bff  mov     ecx, esi; int
0x180041c01  mov     edi, eax
0x180041c03  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041c08  mov     rbx, [rbx+108h]
0x180041c0f  test    rbx, rbx
0x180041c12  jnz     short loc_180041BD9
0x180041c14  mov     rbx, [r14+18h]
0x180041c18  jmp     loc_180041D12
0x180041c1d  mov     rbp, [rbx+8]
0x180041c21  test    rbp, rbp
0x180041c24  jz      loc_180041CFD
0x180041c2a  cmp     dword ptr [rbx+4], 0Ch
0x180041c2e  jbe     loc_180041CFD
0x180041c34  mov     r12d, [rbx+4]
0x180041c38  lea     r14, [rbp+0Ch]
0x180041c3c  add     r12, rbp
0x180041c3f  xor     r13d, r13d
0x180041c42  cmp     r13d, [rbp+8]
0x180041c46  jnb     loc_180041D0E
0x180041c4c  cmp     r14, r12
0x180041c4f  jg      loc_180041CF4
0x180041c55  mov     eax, [r14+4]
0x180041c59  add     rax, r14
0x180041c5c  cmp     rax, r12
0x180041c5f  jg      loc_180041CF4
0x180041c65  mov     ecx, [r14]
0x180041c68  sub     ecx, 1
0x180041c6b  jz      short loc_180041CA1
0x180041c6d  sub     ecx, 1
0x180041c70  jz      short loc_180041C8C
0x180041c72  cmp     ecx, 1
0x180041c75  jnz     short loc_180041CC7
0x180041c77  mov     r9, [r14+8]
0x180041c7b  mov     rcx, r15
0x180041c7e  mov     r8d, [rbp+4]
0x180041c82  mov     edx, [rbx]
0x180041c84  call    cs:__imp_SqmAddToStreamDWord64
0x180041c8a  jmp     short loc_180041CB4
0x180041c8c  mov     r8d, [rbp+4]
0x180041c90  lea     r9, [r14+8]
0x180041c94  mov     edx, [rbx]
0x180041c96  mov     rcx, r15
0x180041c99  call    cs:__imp_SqmAddToStreamString
0x180041c9f  jmp     short loc_180041CB4
0x180041ca1  mov     r9d, [r14+8]
0x180041ca5  mov     rcx, r15
0x180041ca8  mov     r8d, [rbp+4]
0x180041cac  mov     edx, [rbx]
0x180041cae  call    cs:__imp_SqmAddToStreamDWord
0x180041cb4  test    eax, eax
0x180041cb6  jz      short loc_180041CE5
0x180041cb8  mov     eax, [r14+4]
0x180041cbc  add     r14, rax
0x180041cbf  inc     r13d
0x180041cc2  jmp     loc_180041C42
0x180041cc7  call    cs:__imp_GetLastError
0x180041ccd  lea     rdx, aInvalidDataDet; "Invalid data detected in stream entry f"...
0x180041cd4  mov     r8d, [rbx]
0x180041cd7  mov     r9d, eax
0x180041cda  mov     ecx, esi; int
0x180041cdc  mov     edi, eax
0x180041cde  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041ce3  jmp     short loc_180041D0E
0x180041ce5  call    cs:__imp_GetLastError
0x180041ceb  lea     rdx, aAddtostreamCal; "AddToStream call failed for Datapoint %"...
0x180041cf2  jmp     short loc_180041CD4
0x180041cf4  lea     rdx, aInvalidStreamE; "Invalid Stream Entry for Datapoint Id %"...
0x180041cfb  jmp     short loc_180041D04
0x180041cfd  lea     rdx, aInvalidStreamC; "Invalid Stream Cache Entry for Datapint"...
0x180041d04  mov     r8d, [rbx]
0x180041d07  mov     ecx, esi; int
0x180041d09  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041d0e  mov     rbx, [rbx+10h]
0x180041d12  test    rbx, rbx
0x180041d15  jnz     loc_180041C1D
0x180041d1b  mov     eax, edi
0x180041d1d  add     rsp, 28h
0x180041d21  pop     r15
0x180041d23  pop     r14
0x180041d25  pop     r13
0x180041d27  pop     r12
0x180041d29  pop     rdi
0x180041d2a  pop     rsi
0x180041d2b  pop     rbp
0x180041d2c  pop     rbx
0x180041d2d  retn
```
