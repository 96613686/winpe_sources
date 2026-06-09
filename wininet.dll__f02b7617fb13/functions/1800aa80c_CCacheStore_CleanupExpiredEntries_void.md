# CCacheStore::CleanupExpiredEntries(void)

- ea: `0x1800aa80c`
- end: `0x1800aad1c`
- name: `?CleanupExpiredEntries@CCacheStore@@AEAAJXZ`
- size: `1296`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800aea70`

## callees

- `0x180025910`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180083dc4`
- `0x180086300`
- `0x1800aa80c`
- `0x1800aca44`
- `0x1800acab8`
- `0x1800acdb0`
- `0x18014a7a0`
- `0x1801ad900`
- `0x1801e1790`
- `0x1801e25fc`
- `0x1801e3c78`
- `0x1801e4988`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aa908`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aa908`
- `ESENT!JetRetrieveColumn` at `0x1800aa9ef`
- `ESENT!JetRetrieveColumn` at `0x1800aaaa9`
- `ESENT!JetRetrieveColumn` at `0x1800aab63`
- `ESENT!JetRetrieveColumn` at `0x1800aa9ef`
- `ESENT!JetRetrieveColumn` at `0x1800aaaa9`
- `ESENT!JetRetrieveColumn` at `0x1800aab63`
- `ESENT!JetRollback` at `0x1800aacb9`
- `ESENT!JetRollback` at `0x1800aacb9`
- `ESENT!JetBeginTransaction` at `0x1800aa91a`
- `ESENT!JetBeginTransaction` at `0x1800aa91a`
- `ESENT!JetMove` at `0x1800aa959`
- `ESENT!JetMove` at `0x1800aa959`

## pseudocode

```c
__int64 __fastcall CCacheStore::CleanupExpiredEntries(CJetContextList **this)
{
  int BasicColumn; // ebx
  JET_SESID *v4; // rdi
  struct _FILETIME v5; // r15
  JET_ERR v6; // eax
  int i; // esi
  JET_ERR v8; // eax
  JET_ERR v9; // eax
  char v10; // al
  JET_ERR v11; // eax
  char v12; // al
  JET_ERR v13; // eax
  CCacheStore *v14; // rcx
  const unsigned __int16 *v15; // r8
  struct CJetContext *v16; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-29h] BYREF
  unsigned int pcbActual; // [rsp+60h] [rbp-19h] BYREF
  int v19; // [rsp+64h] [rbp-15h]
  unsigned int v20; // [rsp+68h] [rbp-11h] BYREF
  int v21; // [rsp+6Ch] [rbp-Dh] BYREF
  unsigned __int64 v22; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int64 pvData; // [rsp+78h] [rbp-1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int16 *v25[2]; // [rsp+88h] [rbp+Fh] BYREF
  _QWORD v26[2]; // [rsp+98h] [rbp+1Fh] BYREF

  v19 = 0;
  v17[0] = &Data;
  v17[1] = 0;
  v26[0] = &Data;
  v26[1] = 0;
  v25[0] = (unsigned __int16 *)&Data;
  v25[1] = 0;
  v16 = 0;
  pvData = 0;
  v21 = 0;
  v22 = 0;
  SystemTimeAsFileTime = 0;
  v20 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_(1036, 70, WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids);
  BasicColumn = CJetContextList::AcquireContext(this[40], &v16, 0);
  if ( BasicColumn >= 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = (JET_SESID *)v16;
    v5 = SystemTimeAsFileTime;
    v6 = JetBeginTransaction(*((_QWORD *)v16 + 2));
    BasicColumn = HRESULTFromJET_ERR(v6, 1);
    if ( BasicColumn >= 0 )
    {
      for ( i = 0x80000000; !(unsigned int)CCacheStore::IsTerminating((CCacheStore *)this); i = 1 )
      {
        v8 = JetMove(v4[2], v4[4], i, 0);
        if ( v8 == -1603 )
          break;
        BasicColumn = HRESULTFromJET_ERR(v8, 1);
        if ( BasicColumn < 0 )
          break;
        pcbActual = 0;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 0, (__int64)&pvData);
        v9 = JetRetrieveColumn(v4[2], v4[4], **(_DWORD **)(v4[5] + 8), &pvData, 8u, &pcbActual, 0, 0);
        BasicColumn = HRESULTFromJET_ERR(v9, 1);
        if ( BasicColumn >= 0 )
        {
          if ( pcbActual == 8 )
            BasicColumn = 0;
          else
            BasicColumn = -2147418113;
        }
        v10 = BYTE1(xmmword_180266B60);
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        {
          WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)BasicColumn);
          v10 = BYTE1(xmmword_180266B60);
        }
        if ( BasicColumn < 0 )
        {
          v19 = 3152;
          break;
        }
        pcbActual = 0;
        if ( (v10 & 0x10) != 0 )
          WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 4, (__int64)&v21);
        v11 = JetRetrieveColumn(v4[2], v4[4], *(_DWORD *)(*(_QWORD *)(v4[5] + 8) + 16LL), &v21, 4u, &pcbActual, 0, 0);
        BasicColumn = HRESULTFromJET_ERR(v11, 1);
        if ( BasicColumn >= 0 )
        {
          if ( pcbActual == 4 )
            BasicColumn = 0;
          else
            BasicColumn = -2147418113;
        }
        v12 = BYTE1(xmmword_180266B60);
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        {
          WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)BasicColumn);
          v12 = BYTE1(xmmword_180266B60);
        }
        if ( BasicColumn < 0 )
        {
          v19 = 3154;
          break;
        }
        pcbActual = 0;
        if ( (v12 & 0x10) != 0 )
          WPP_SF_dqd(1036, 17, (unsigned int)WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 12, (__int64)&v20);
        v13 = JetRetrieveColumn(v4[2], v4[4], *(_DWORD *)(*(_QWORD *)(v4[5] + 8) + 48LL), &v20, 4u, &pcbActual, 0, 0);
        BasicColumn = HRESULTFromJET_ERR(v13, 1);
        if ( BasicColumn >= 0 )
        {
          if ( pcbActual == 4 )
            BasicColumn = 0;
          else
            BasicColumn = -2147418113;
        }
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 18, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)BasicColumn);
        if ( BasicColumn < 0 )
        {
          v19 = 3158;
          break;
        }
        if ( v20 )
        {
          BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v4, 0xBu, &v22, 8u);
          if ( BasicColumn < 0 )
          {
            v19 = 3170;
            break;
          }
          if ( *(_QWORD *)&v5 <= v22 || (*(_QWORD *)&v5 - v22) / 0x989680 >= (unsigned __int64)v20 >> 1 )
          {
            BasicColumn = CJetContext::GetStringColumn((CJetContext *)v4, 7u, (struct CWxString *)v26);
            if ( BasicColumn < 0 )
            {
              v19 = 3186;
              break;
            }
            BasicColumn = CJetContext::GetStringColumn((CJetContext *)v4, 1u, (struct CWxString *)v25);
            if ( BasicColumn < 0 )
            {
              v19 = 3188;
              break;
            }
            if ( (unsigned int)CCacheStore::IsPartitionOffline(v14, v25[0], v15) )
            {
              BasicColumn = CCacheStore::ScavengeExpiredEntries((CCacheStore *)this, pvData, v20);
              if ( BasicColumn < 0 )
              {
                v19 = 3195;
                break;
              }
            }
          }
        }
      }
      JetRollback(v4[2], 0);
    }
  }
  else
  {
    v19 = 3127;
  }
  CCacheStore::ReleaseContainerContext((CCacheStore *)this, &v16);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qD(1036, 71, WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids, this, BasicColumn);
  CWxString::_Release((CWxString *)v25);
  CWxString::_Release((CWxString *)v26);
  CWxString::_Release((CWxString *)v17);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x1800aa80c  mov     [rsp-8+arg_8], rbx
0x1800aa811  mov     [rsp-8+arg_10], rsi
0x1800aa816  push    rbp
0x1800aa817  push    rdi
0x1800aa818  push    r12
0x1800aa81a  push    r14
0x1800aa81c  push    r15
0x1800aa81e  lea     rbp, [rsp-37h]
0x1800aa823  sub     rsp, 0B0h
0x1800aa82a  mov     rax, cs:__security_cookie
0x1800aa831  xor     rax, rsp
0x1800aa834  mov     [rbp+57h+var_28], rax
0x1800aa838  xor     r12d, r12d
0x1800aa83b  lea     rax, Data
0x1800aa842  mov     [rbp+57h+var_6C], r12d
0x1800aa846  mov     r14, rcx
0x1800aa849  mov     [rbp+57h+var_80], rax
0x1800aa84d  mov     [rbp+57h+var_78], r12
0x1800aa851  mov     [rbp+57h+var_38], rax
0x1800aa855  mov     [rbp+57h+var_30], r12
0x1800aa859  mov     [rbp+57h+var_48], rax
0x1800aa85d  mov     [rbp+57h+var_40], r12
0x1800aa861  mov     [rbp+57h+var_88], r12
0x1800aa865  mov     [rbp+57h+pvData], r12
0x1800aa869  mov     [rbp+57h+var_64], r12d
0x1800aa86d  mov     [rbp+57h+var_60], r12
0x1800aa871  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800aa875  mov     [rbp+57h+var_68], r12d
0x1800aa879  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800aa880  jnz     loc_1800AABEB
0x1800aa886  mov     rcx, [r14+140h]; this
0x1800aa88d  lea     rdx, [rbp+57h+var_88]; struct CJetContext **
0x1800aa891  xor     r8d, r8d; int *
0x1800aa894  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800aa899  mov     ebx, eax
0x1800aa89b  test    eax, eax
0x1800aa89d  jns     short loc_1800AA904
0x1800aa89f  mov     [rbp+57h+var_6C], 0C37h
0x1800aa8a6  lea     rdx, [rbp+57h+var_88]; struct CJetContext **
0x1800aa8aa  mov     rcx, r14; this
0x1800aa8ad  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1800aa8b2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800aa8b9  jnz     loc_1800AACFA
0x1800aa8bf  lea     rcx, [rbp+57h+var_48]; this
0x1800aa8c3  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800aa8c8  lea     rcx, [rbp+57h+var_38]; this
0x1800aa8cc  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800aa8d1  lea     rcx, [rbp+57h+var_80]; this
0x1800aa8d5  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800aa8da  mov     eax, ebx
0x1800aa8dc  mov     rcx, [rbp+57h+var_28]
0x1800aa8e0  xor     rcx, rsp; StackCookie
0x1800aa8e3  call    __security_check_cookie
0x1800aa8e8  lea     r11, [rsp+0D0h+var_20]
0x1800aa8f0  mov     rbx, [r11+38h]
0x1800aa8f4  mov     rsi, [r11+40h]
0x1800aa8f8  mov     rsp, r11
0x1800aa8fb  pop     r15
0x1800aa8fd  pop     r14
0x1800aa8ff  pop     r12
0x1800aa901  pop     rdi
0x1800aa902  pop     rbp
0x1800aa903  retn
0x1800aa904  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800aa908  call    cs:__imp_GetSystemTimeAsFileTime
0x1800aa90e  mov     rdi, [rbp+57h+var_88]
0x1800aa912  mov     r15, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800aa916  mov     rcx, [rdi+10h]; sesid
0x1800aa91a  call    cs:__imp_JetBeginTransaction
0x1800aa920  mov     ecx, eax; int
0x1800aa922  mov     edx, 1; int
0x1800aa927  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aa92c  mov     ebx, eax
0x1800aa92e  test    eax, eax
0x1800aa930  js      loc_1800AA8A6
0x1800aa936  mov     esi, 80000000h
0x1800aa93b  mov     rcx, r14; this
0x1800aa93e  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800aa943  test    eax, eax
0x1800aa945  jnz     loc_1800AACB3
0x1800aa94b  mov     rdx, [rdi+20h]; tableid
0x1800aa94f  xor     r9d, r9d; grbit
0x1800aa952  mov     rcx, [rdi+10h]; sesid
0x1800aa956  mov     r8d, esi; cRow
0x1800aa959  call    cs:__imp_JetMove
0x1800aa95f  cmp     eax, 0FFFFF9BDh
0x1800aa964  jz      loc_1800AACB3
0x1800aa96a  mov     edx, 1; int
0x1800aa96f  mov     ecx, eax; int
0x1800aa971  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aa976  mov     ebx, eax
0x1800aa978  test    eax, eax
0x1800aa97a  js      loc_1800AACB3
0x1800aa980  mov     [rbp+57h+var_8C], r12d
0x1800aa984  mov     [rbp+57h+var_70], r12d
0x1800aa988  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800aa98f  mov     esi, 40Ch
0x1800aa994  jz      short loc_1800AA9BD
0x1800aa996  lea     rax, [rbp+57h+pvData]
0x1800aa99a  mov     dword ptr [rsp+0D0h+pcbActual], 8
0x1800aa9a2  mov     edx, 11h
0x1800aa9a7  mov     qword ptr [rsp+0D0h+cbData], rax
0x1800aa9ac  mov     ecx, esi
0x1800aa9ae  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800aa9b5  xor     r9d, r9d
0x1800aa9b8  call    WPP_SF_dqd
0x1800aa9bd  mov     rax, [rdi+28h]
0x1800aa9c1  lea     r9, [rbp+57h+pvData]; pvData
0x1800aa9c5  mov     rdx, [rdi+20h]; tableid
0x1800aa9c9  mov     rcx, [rdi+10h]; sesid
0x1800aa9cd  mov     [rsp+0D0h+pretinfo], r12; pretinfo
0x1800aa9d2  mov     r8, [rax+8]
0x1800aa9d6  lea     rax, [rbp+57h+var_70]
0x1800aa9da  mov     [rsp+0D0h+grbit], r12d; grbit
0x1800aa9df  mov     [rsp+0D0h+pcbActual], rax; pcbActual
0x1800aa9e4  mov     [rsp+0D0h+cbData], 8; cbData
0x1800aa9ec  mov     r8d, [r8]; columnid
0x1800aa9ef  call    cs:__imp_JetRetrieveColumn
0x1800aa9f5  mov     ecx, eax; int
0x1800aa9f7  mov     edx, 1; int
0x1800aa9fc  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aaa01  mov     ebx, eax
0x1800aaa03  test    eax, eax
0x1800aaa05  js      short loc_1800AAA14
0x1800aaa07  cmp     [rbp+57h+var_70], 8
0x1800aaa0b  jnz     loc_1800AABBB
0x1800aaa11  mov     ebx, r12d
0x1800aaa14  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800aaa1a  test    al, 10h
0x1800aaa1c  jz      short loc_1800AAA3A
0x1800aaa1e  mov     edx, 12h
0x1800aaa23  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800aaa2a  mov     ecx, esi
0x1800aaa2c  mov     r9d, ebx
0x1800aaa2f  call    WPP_SF_d
0x1800aaa34  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800aaa3a  test    ebx, ebx
0x1800aaa3c  js      loc_1800AACF1
0x1800aaa42  mov     [rbp+57h+var_8C], r12d
0x1800aaa46  mov     [rbp+57h+var_70], r12d
0x1800aaa4a  test    al, 10h
0x1800aaa4c  jz      short loc_1800AAA76
0x1800aaa4e  mov     edx, 11h
0x1800aaa53  lea     rax, [rbp+57h+var_64]
0x1800aaa57  mov     ecx, esi
0x1800aaa59  lea     r8d, [rdx-0Dh]
0x1800aaa5d  mov     dword ptr [rsp+0D0h+pcbActual], r8d
0x1800aaa62  mov     r9d, r8d
0x1800aaa65  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800aaa6c  mov     qword ptr [rsp+0D0h+cbData], rax
0x1800aaa71  call    WPP_SF_dqd
0x1800aaa76  mov     rax, [rdi+28h]
0x1800aaa7a  lea     r9, [rbp+57h+var_64]; pvData
0x1800aaa7e  mov     rdx, [rdi+20h]; tableid
0x1800aaa82  mov     rcx, [rdi+10h]; sesid
0x1800aaa86  mov     [rsp+0D0h+pretinfo], r12; pretinfo
0x1800aaa8b  mov     r8, [rax+8]
0x1800aaa8f  lea     rax, [rbp+57h+var_70]
0x1800aaa93  mov     [rsp+0D0h+grbit], r12d; grbit
0x1800aaa98  mov     [rsp+0D0h+pcbActual], rax; pcbActual
0x1800aaa9d  mov     [rsp+0D0h+cbData], 4; cbData
0x1800aaaa5  mov     r8d, [r8+10h]; columnid
0x1800aaaa9  call    cs:__imp_JetRetrieveColumn
0x1800aaaaf  mov     ecx, eax; int
0x1800aaab1  mov     edx, 1; int
0x1800aaab6  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aaabb  mov     ebx, eax
0x1800aaabd  test    eax, eax
0x1800aaabf  js      short loc_1800AAACE
0x1800aaac1  cmp     [rbp+57h+var_70], 4
0x1800aaac5  jnz     loc_1800AABCC
0x1800aaacb  mov     ebx, r12d
0x1800aaace  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800aaad4  test    al, 10h
0x1800aaad6  jz      short loc_1800AAAF4
0x1800aaad8  mov     edx, 12h
0x1800aaadd  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800aaae4  mov     ecx, esi
0x1800aaae6  mov     r9d, ebx
0x1800aaae9  call    WPP_SF_d
0x1800aaaee  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800aaaf4  test    ebx, ebx
0x1800aaaf6  js      loc_1800AACE8
0x1800aaafc  mov     [rbp+57h+var_8C], r12d
0x1800aab00  mov     [rbp+57h+var_70], r12d
0x1800aab04  test    al, 10h
0x1800aab06  jz      short loc_1800AAB30
0x1800aab08  mov     edx, 11h
0x1800aab0d  mov     dword ptr [rsp+0D0h+pcbActual], 4
0x1800aab15  lea     rax, [rbp+57h+var_68]
0x1800aab19  mov     ecx, esi
0x1800aab1b  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800aab22  mov     qword ptr [rsp+0D0h+cbData], rax
0x1800aab27  lea     r9d, [rdx-5]
0x1800aab2b  call    WPP_SF_dqd
0x1800aab30  mov     rax, [rdi+28h]
0x1800aab34  lea     r9, [rbp+57h+var_68]; pvData
0x1800aab38  mov     rdx, [rdi+20h]; tableid
0x1800aab3c  mov     rcx, [rdi+10h]; sesid
0x1800aab40  mov     [rsp+0D0h+pretinfo], r12; pretinfo
0x1800aab45  mov     r8, [rax+8]
0x1800aab49  lea     rax, [rbp+57h+var_70]
0x1800aab4d  mov     [rsp+0D0h+grbit], r12d; grbit
0x1800aab52  mov     [rsp+0D0h+pcbActual], rax; pcbActual
0x1800aab57  mov     [rsp+0D0h+cbData], 4; cbData
0x1800aab5f  mov     r8d, [r8+30h]; columnid
0x1800aab63  call    cs:__imp_JetRetrieveColumn
0x1800aab69  mov     ecx, eax; int
0x1800aab6b  mov     edx, 1; int
0x1800aab70  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aab75  mov     ebx, eax
0x1800aab77  test    eax, eax
0x1800aab79  js      short loc_1800AAB84
0x1800aab7b  cmp     [rbp+57h+var_70], 4
0x1800aab7f  jnz     short loc_1800AABDD
0x1800aab81  mov     ebx, r12d
0x1800aab84  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800aab8b  jz      short loc_1800AABA3
0x1800aab8d  mov     edx, 12h
0x1800aab92  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800aab99  mov     ecx, esi
0x1800aab9b  mov     r9d, ebx
0x1800aab9e  call    WPP_SF_d
0x1800aaba3  test    ebx, ebx
0x1800aaba5  js      loc_1800AACDF
0x1800aabab  cmp     [rbp+57h+var_68], r12d
0x1800aabaf  jnz     short loc_1800AAC06
0x1800aabb1  mov     esi, 1
0x1800aabb6  jmp     loc_1800AA93B
0x1800aabbb  mov     ebx, 8000FFFFh
0x1800aabc0  mov     [rbp+57h+var_8C], 0D6h
0x1800aabc7  jmp     loc_1800AAA14
0x1800aabcc  mov     ebx, 8000FFFFh
0x1800aabd1  mov     [rbp+57h+var_8C], 0D6h
0x1800aabd8  jmp     loc_1800AAACE
0x1800aabdd  mov     ebx, 8000FFFFh
0x1800aabe2  mov     [rbp+57h+var_8C], 0D6h
0x1800aabe9  jmp     short loc_1800AAB84
0x1800aabeb  mov     edx, 46h ; 'F'
0x1800aabf0  lea     r8, WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids
0x1800aabf7  mov     ecx, 40Ch
0x1800aabfc  call    WPP_SF_
0x1800aac01  jmp     loc_1800AA886
0x1800aac06  mov     r9d, 8; unsigned int
0x1800aac0c  lea     r8, [rbp+57h+var_60]; void *
0x1800aac10  mov     rcx, rdi; this
0x1800aac13  lea     edx, [r9+3]; unsigned int
0x1800aac17  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800aac1c  mov     ebx, eax
0x1800aac1e  test    eax, eax
0x1800aac20  js      loc_1800AACD6
0x1800aac26  cmp     r15, [rbp+57h+var_60]
0x1800aac2a  jbe     short loc_1800AAC53
0x1800aac2c  mov     rcx, r15
0x1800aac2f  mov     rax, 0D6BF94D5E57A42BDh
0x1800aac39  sub     rcx, [rbp+57h+var_60]
0x1800aac3d  mul     rcx
0x1800aac40  mov     eax, [rbp+57h+var_68]
0x1800aac43  shr     rdx, 17h
0x1800aac47  shr     rax, 1
0x1800aac4a  cmp     rdx, rax
0x1800aac4d  jb      loc_1800AABB1
0x1800aac53  lea     r8, [rbp+57h+var_38]; struct CWxString *
0x1800aac57  mov     edx, 7; unsigned int
0x1800aac5c  mov     rcx, rdi; this
0x1800aac5f  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800aac64  mov     ebx, eax
0x1800aac66  test    eax, eax
0x1800aac68  js      short loc_1800AACCD
0x1800aac6a  lea     r8, [rbp+57h+var_48]; struct CWxString *
0x1800aac6e  mov     edx, 1; unsigned int
0x1800aac73  mov     rcx, rdi; this
0x1800aac76  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800aac7b  mov     ebx, eax
0x1800aac7d  test    eax, eax
0x1800aac7f  js      short loc_1800AACC4
0x1800aac81  mov     rdx, [rbp+57h+var_48]; unsigned __int16 *
0x1800aac85  call    ?IsPartitionOffline@CCacheStore@@AEAAJPEBG0@Z; CCacheStore::IsPartitionOffline(ushort const *,ushort const *)
0x1800aac8a  test    eax, eax
0x1800aac8c  jz      loc_1800AABB1
0x1800aac92  mov     r8d, [rbp+57h+var_68]; unsigned int
0x1800aac96  mov     rcx, r14; this
0x1800aac99  mov     rdx, [rbp+57h+pvData]; unsigned __int64
0x1800aac9d  call    ?ScavengeExpiredEntries@CCacheStore@@AEAAJ_KK@Z; CCacheStore::ScavengeExpiredEntries(unsigned __int64,ulong)
0x1800aaca2  mov     ebx, eax
0x1800aaca4  test    eax, eax
0x1800aaca6  jns     loc_1800AABB1
0x1800aacac  mov     [rbp+57h+var_6C], 0C7Bh
0x1800aacb3  mov     rcx, [rdi+10h]; sesid
0x1800aacb7  xor     edx, edx; grbit
0x1800aacb9  call    cs:__imp_JetRollback
0x1800aacbf  jmp     loc_1800AA8A6
0x1800aacc4  mov     [rbp+57h+var_6C], 0C74h
0x1800aaccb  jmp     short loc_1800AACB3
0x1800aaccd  mov     [rbp+57h+var_6C], 0C72h
0x1800aacd4  jmp     short loc_1800AACB3
0x1800aacd6  mov     [rbp+57h+var_6C], 0C62h
0x1800aacdd  jmp     short loc_1800AACB3
0x1800aacdf  mov     [rbp+57h+var_6C], 0C56h
0x1800aace6  jmp     short loc_1800AACB3
  ... truncated ...
```
