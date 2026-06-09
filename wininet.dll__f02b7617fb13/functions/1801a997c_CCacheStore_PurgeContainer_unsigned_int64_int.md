# CCacheStore::PurgeContainer(unsigned __int64,int)

- ea: `0x1801a997c`
- end: `0x1801a9cfb`
- name: `?PurgeContainer@CCacheStore@@AEAAJ_KH@Z`
- size: `895`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this, unsigned __int64, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001f5fc`
- `0x1800aad24`

## callees

- `0x18001f3a4`
- `0x1800201a0`
- `0x180021360`
- `0x180021fec`
- `0x180025910`
- `0x18007ec9c`
- `0x180086300`
- `0x180097e10`
- `0x1800e28e0`
- `0x1800ee168`
- `0x1800eed94`
- `0x1800eee94`
- `0x1800fa844`
- `0x18012ad34`
- `0x18014a7a0`
- `0x1801a997c`
- `0x1801dc2f8`
- `0x1801e1790`

## import_xrefs

- `ESENT!JetDeleteTableW` at `0x1801a9b15`
- `ESENT!JetDeleteTableW` at `0x1801a9b15`
- `ESENT!JetDelete` at `0x1801a9b42`
- `ESENT!JetDelete` at `0x1801a9b42`
- `ESENT!JetCommitTransaction` at `0x1801a9cdd`
- `ESENT!JetCommitTransaction` at `0x1801a9cdd`
- `ESENT!JetUpdate` at `0x1801a9cbe`
- `ESENT!JetUpdate` at `0x1801a9cbe`
- `ESENT!JetPrepareUpdate` at `0x1801a9b62`
- `ESENT!JetPrepareUpdate` at `0x1801a9baf`
- `ESENT!JetPrepareUpdate` at `0x1801a9b62`
- `ESENT!JetPrepareUpdate` at `0x1801a9baf`
- `ESENT!JetRollback` at `0x1801a9bbb`
- `ESENT!JetRollback` at `0x1801a9bbb`
- `ESENT!JetBeginTransaction` at `0x1801a9aa1`
- `ESENT!JetBeginTransaction` at `0x1801a9aa1`

## pseudocode

```c
__int64 __fastcall CCacheStore::PurgeContainer(CCacheStore *this, unsigned __int64 a2, __int64 a3)
{
  int v3; // r12d
  int v6; // eax
  int v7; // ebx
  unsigned int v8; // r9d
  CJetContext *v9; // rdi
  JET_ERR v10; // eax
  int v11; // eax
  JET_ERR v12; // eax
  JET_TABLEID v13; // rdx
  JET_SESID v14; // rcx
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  CJetContext *v20; // [rsp+38h] [rbp-48h] BYREF
  CContainerProps *v21; // [rsp+40h] [rbp-40h] BYREF
  char *v22; // [rsp+48h] [rbp-38h] BYREF
  __int64 v23; // [rsp+50h] [rbp-30h]
  JET_PCWSTR szTableName[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v25; // [rsp+68h] [rbp-18h] BYREF

  v22 = (char *)this + 280;
  v3 = a3;
  v23 = 0;
  szTableName[0] = &Data;
  v21 = 0;
  v20 = 0;
  szTableName[1] = 0;
  v25 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qil(this, a2, a3, this, a2, a3);
  AutoCritSec::Lock((AutoCritSec *)&v22);
  *(_QWORD *)(*((_QWORD *)this + 42) + 8LL) = a2;
  v6 = CWxRefMap<CContainerPropsMap,CContainerProps>::Find(*((_QWORD *)this + 41), *((_QWORD *)this + 42), &v21);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( !v6 )
    {
      v7 = 1;
      goto LABEL_22;
    }
    v7 = CCacheStore::AcquireContainerContext(this, &v20);
    if ( v7 >= 0 )
    {
      v9 = v20;
      v7 = CJetContext::SetCurrentIndex(v20, 0, L"ContainerIdIndex", v8);
      if ( v7 >= 0 )
      {
        v10 = JetBeginTransaction(*((_QWORD *)v9 + 2));
        v7 = HRESULTFromJET_ERR(v10, 1);
        if ( v7 >= 0 )
        {
          v11 = SeekToContainer(v9, a2);
          v7 = v11;
          if ( v11 < 0 )
          {
LABEL_21:
            JetRollback(*((_QWORD *)v9 + 2), 0);
            goto LABEL_22;
          }
          if ( v11 )
          {
            v7 = 0;
            goto LABEL_21;
          }
          v7 = CWxString::Format((CWxString *)szTableName, L"Container_%I64u", a2);
          if ( v7 < 0 )
            goto LABEL_21;
          v12 = JetDeleteTableW(*((_QWORD *)v9 + 2), *((_DWORD *)v9 + 6), szTableName[0]);
          if ( v12 != -1305 )
          {
            v7 = HRESULTFromJET_ERR(v12, 1);
            if ( v7 < 0 )
              goto LABEL_21;
          }
          v13 = *((_QWORD *)v9 + 4);
          v14 = *((_QWORD *)v9 + 2);
          if ( v3 )
          {
            v15 = JetDelete(v14, v13);
            v7 = HRESULTFromJET_ERR(v15, 1);
            if ( v7 < 0 )
              goto LABEL_21;
          }
          else
          {
            v16 = JetPrepareUpdate(v14, v13, 2u);
            v7 = HRESULTFromJET_ERR(v16, 1);
            if ( v7 < 0 )
              goto LABEL_21;
            v7 = CJetContext::SetBasicColumn(v9, 5u, &v25, 8u);
            if ( v7 < 0
              || (v7 = CJetContext::SetStringColumn(v9, 8u, 0), v7 < 0)
              || (v7 = CJetContext::SetBinaryColumn(v9, 9u, 0, 0), v7 < 0)
              || (v7 = CJetContext::SetBinaryColumn(v9, 0xAu, 0, 0), v7 < 0)
              || (v18 = JetUpdate(*((_QWORD *)v9 + 2), *((_QWORD *)v9 + 4), 0, 0, 0),
                  v7 = HRESULTFromJET_ERR(v18, 1),
                  v7 < 0) )
            {
              JetPrepareUpdate(*((_QWORD *)v9 + 2), *((_QWORD *)v9 + 4), 3u);
              goto LABEL_21;
            }
          }
          v19 = JetCommitTransaction(*((_QWORD *)v9 + 2), 1u);
          v7 = HRESULTFromJET_ERR(v19, 1);
          if ( v7 < 0 )
            goto LABEL_21;
        }
      }
    }
  }
LABEL_22:
  CCacheStore::ReleaseContainerContext(this, &v20);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 45, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)v7);
  CWxString::_Release((CWxString *)szTableName);
  if ( v21 )
    CContainerProps::Release(v21);
  if ( (_DWORD)v23 )
    AutoCritSec::Unlock((AutoCritSec *)&v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801a997c  mov     [rsp-28h+arg_10], rbx
0x1801a9981  mov     [rsp-28h+arg_18], rsi
0x1801a9986  push    rbp
0x1801a9987  push    rdi
0x1801a9988  push    r12
0x1801a998a  push    r14
0x1801a998c  push    r15
0x1801a998e  mov     rbp, rsp
0x1801a9991  sub     rsp, 80h
0x1801a9998  mov     rax, cs:__security_cookie
0x1801a999f  xor     rax, rsp
0x1801a99a2  mov     [rbp+var_10], rax
0x1801a99a6  lea     rax, [rcx+118h]
0x1801a99ad  mov     [rbp+var_4C], 0
0x1801a99b4  mov     [rbp+var_38], rax
0x1801a99b8  mov     r12d, r8d
0x1801a99bb  lea     rax, Data
0x1801a99c2  mov     [rbp+var_30], 0
0x1801a99ca  mov     [rbp+szTableName], rax
0x1801a99ce  mov     r14, rdx
0x1801a99d1  mov     r15, rcx
0x1801a99d4  mov     [rbp+var_40], 0
0x1801a99dc  mov     [rbp+var_48], 0
0x1801a99e4  mov     [rbp+var_20], 0
0x1801a99ec  mov     [rbp+var_18], 0
0x1801a99f4  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a99fb  jz      short loc_1801A9A0F
0x1801a99fd  mov     [rsp+80h+var_58], r8d
0x1801a9a02  mov     r9, rcx
0x1801a9a05  mov     [rsp+80h+pcbActual], rdx
0x1801a9a0a  call    WPP_SF_qil
0x1801a9a0f  lea     rcx, [rbp+var_38]; this
0x1801a9a13  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x1801a9a18  mov     rax, [r15+150h]
0x1801a9a1f  lea     r8, [rbp+var_40]
0x1801a9a23  mov     [rax+8], r14
0x1801a9a27  mov     rdx, [r15+150h]
0x1801a9a2e  mov     rcx, [r15+148h]
0x1801a9a35  call    ?Find@?$CWxRefMap@VCContainerPropsMap@@VCContainerProps@@@@QEAAJPEAVCContainerProps@@PEAPEAV2@@Z; CWxRefMap<CContainerPropsMap,CContainerProps>::Find(CContainerProps *,CContainerProps * *)
0x1801a9a3a  mov     ebx, eax
0x1801a9a3c  test    eax, eax
0x1801a9a3e  jns     short loc_1801A9A4C
0x1801a9a40  mov     [rbp+var_4C], 902h
0x1801a9a47  jmp     loc_1801A9BC1
0x1801a9a4c  jnz     short loc_1801A9A58
0x1801a9a4e  mov     ebx, 1
0x1801a9a53  jmp     loc_1801A9BC1
0x1801a9a58  lea     rdx, [rbp+var_48]; struct CJetContext **
0x1801a9a5c  mov     rcx, r15; this
0x1801a9a5f  call    ?AcquireContainerContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquireContainerContext(CJetContext * *)
0x1801a9a64  mov     ebx, eax
0x1801a9a66  test    eax, eax
0x1801a9a68  jns     short loc_1801A9A76
0x1801a9a6a  mov     [rbp+var_4C], 90Bh
0x1801a9a71  jmp     loc_1801A9BC1
0x1801a9a76  mov     rdi, [rbp+var_48]
0x1801a9a7a  lea     r8, aContaineridind; "ContainerIdIndex"
0x1801a9a81  mov     rcx, rdi; this
0x1801a9a84  xor     edx, edx; unsigned int
0x1801a9a86  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801a9a8b  mov     ebx, eax
0x1801a9a8d  test    eax, eax
0x1801a9a8f  jns     short loc_1801A9A9D
0x1801a9a91  mov     [rbp+var_4C], 90Ch
0x1801a9a98  jmp     loc_1801A9BC1
0x1801a9a9d  mov     rcx, [rdi+10h]; sesid
0x1801a9aa1  call    cs:__imp_JetBeginTransaction
0x1801a9aa7  mov     esi, 1
0x1801a9aac  mov     ecx, eax; int
0x1801a9aae  mov     edx, esi; int
0x1801a9ab0  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9ab5  mov     ebx, eax
0x1801a9ab7  test    eax, eax
0x1801a9ab9  js      loc_1801A9BC1
0x1801a9abf  mov     rdx, r14; unsigned __int64
0x1801a9ac2  mov     rcx, rdi; struct CJetContext *
0x1801a9ac5  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x1801a9aca  mov     ebx, eax
0x1801a9acc  test    eax, eax
0x1801a9ace  jns     short loc_1801A9ADC
0x1801a9ad0  mov     [rbp+var_4C], 911h
0x1801a9ad7  jmp     loc_1801A9BB5
0x1801a9adc  jz      short loc_1801A9AE5
0x1801a9ade  xor     ebx, ebx
0x1801a9ae0  jmp     loc_1801A9BB5
0x1801a9ae5  mov     r8, r14
0x1801a9ae8  lea     rdx, ?c_wszEntryTable@@3QBGB; "Container_%I64u"
0x1801a9aef  lea     rcx, [rbp+szTableName]; this
0x1801a9af3  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1801a9af8  mov     ebx, eax
0x1801a9afa  test    eax, eax
0x1801a9afc  jns     short loc_1801A9B0A
0x1801a9afe  mov     [rbp+var_4C], 91Dh
0x1801a9b05  jmp     loc_1801A9BB5
0x1801a9b0a  mov     r8, [rbp+szTableName]; szTableName
0x1801a9b0e  mov     edx, [rdi+18h]; dbid
0x1801a9b11  mov     rcx, [rdi+10h]; sesid
0x1801a9b15  call    cs:__imp_JetDeleteTableW
0x1801a9b1b  cmp     eax, 0FFFFFAE7h
0x1801a9b20  jz      short loc_1801A9B35
0x1801a9b22  mov     edx, esi; int
0x1801a9b24  mov     ecx, eax; int
0x1801a9b26  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9b2b  mov     ebx, eax
0x1801a9b2d  test    eax, eax
0x1801a9b2f  js      loc_1801A9BB5
0x1801a9b35  mov     rdx, [rdi+20h]; tableid
0x1801a9b39  mov     rcx, [rdi+10h]; sesid
0x1801a9b3d  test    r12d, r12d
0x1801a9b40  jz      short loc_1801A9B5C
0x1801a9b42  call    cs:__imp_JetDelete
0x1801a9b48  mov     ecx, eax; int
0x1801a9b4a  mov     edx, esi; int
0x1801a9b4c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9b51  mov     ebx, eax
0x1801a9b53  test    eax, eax
0x1801a9b55  js      short loc_1801A9BB5
0x1801a9b57  jmp     loc_1801A9CD7
0x1801a9b5c  mov     r8d, 2; prep
0x1801a9b62  call    cs:__imp_JetPrepareUpdate
0x1801a9b68  mov     ecx, eax; int
0x1801a9b6a  mov     edx, esi; int
0x1801a9b6c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9b71  mov     ebx, eax
0x1801a9b73  test    eax, eax
0x1801a9b75  js      short loc_1801A9BB5
0x1801a9b77  mov     r14d, 8
0x1801a9b7d  lea     r8, [rbp+var_18]; void *
0x1801a9b81  mov     r9d, r14d; unsigned int
0x1801a9b84  mov     rcx, rdi; this
0x1801a9b87  lea     edx, [r14-3]; unsigned int
0x1801a9b8b  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801a9b90  mov     ebx, eax
0x1801a9b92  test    eax, eax
0x1801a9b94  jns     loc_1801A9C3F
0x1801a9b9a  mov     [rbp+var_4C], 938h
0x1801a9ba1  mov     rdx, [rdi+20h]; tableid
0x1801a9ba5  mov     r8d, 3; prep
0x1801a9bab  mov     rcx, [rdi+10h]; sesid
0x1801a9baf  call    cs:__imp_JetPrepareUpdate
0x1801a9bb5  mov     rcx, [rdi+10h]; sesid
0x1801a9bb9  xor     edx, edx; grbit
0x1801a9bbb  call    cs:__imp_JetRollback
0x1801a9bc1  lea     rdx, [rbp+var_48]; struct CJetContext **
0x1801a9bc5  mov     rcx, r15; this
0x1801a9bc8  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1801a9bcd  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a9bd4  jz      short loc_1801A9BEF
0x1801a9bd6  mov     edx, 2Dh ; '-'
0x1801a9bdb  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a9be2  mov     ecx, 40Ch
0x1801a9be7  mov     r9d, ebx
0x1801a9bea  call    WPP_SF_d
0x1801a9bef  lea     rcx, [rbp+szTableName]; this
0x1801a9bf3  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1801a9bf8  mov     rcx, [rbp+var_40]; this
0x1801a9bfc  test    rcx, rcx
0x1801a9bff  jz      short loc_1801A9C06
0x1801a9c01  call    ?Release@CContainerProps@@QEAAKXZ; CContainerProps::Release(void)
0x1801a9c06  cmp     dword ptr [rbp+var_30], 0
0x1801a9c0a  jz      short loc_1801A9C15
0x1801a9c0c  lea     rcx, [rbp+var_38]; this
0x1801a9c10  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801a9c15  mov     eax, ebx
0x1801a9c17  mov     rcx, [rbp+var_10]
0x1801a9c1b  xor     rcx, rsp; StackCookie
0x1801a9c1e  call    __security_check_cookie
0x1801a9c23  lea     r11, [rsp+80h+var_s0]
0x1801a9c2b  mov     rbx, [r11+40h]
0x1801a9c2f  mov     rsi, [r11+48h]
0x1801a9c33  mov     rsp, r11
0x1801a9c36  pop     r15
0x1801a9c38  pop     r14
0x1801a9c3a  pop     r12
0x1801a9c3c  pop     rdi
0x1801a9c3d  pop     rbp
0x1801a9c3e  retn
0x1801a9c3f  xor     r8d, r8d; unsigned __int16 *
0x1801a9c42  mov     edx, r14d; unsigned int
0x1801a9c45  mov     rcx, rdi; this
0x1801a9c48  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1801a9c4d  mov     ebx, eax
0x1801a9c4f  test    eax, eax
0x1801a9c51  jns     short loc_1801A9C5F
0x1801a9c53  mov     [rbp+var_4C], 939h
0x1801a9c5a  jmp     loc_1801A9BA1
0x1801a9c5f  xor     r9d, r9d; unsigned int
0x1801a9c62  xor     r8d, r8d; unsigned __int8 *
0x1801a9c65  mov     rcx, rdi; this
0x1801a9c68  lea     edx, [r9+9]; unsigned int
0x1801a9c6c  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1801a9c71  mov     ebx, eax
0x1801a9c73  test    eax, eax
0x1801a9c75  jns     short loc_1801A9C83
0x1801a9c77  mov     [rbp+var_4C], 93Ah
0x1801a9c7e  jmp     loc_1801A9BA1
0x1801a9c83  xor     r9d, r9d; unsigned int
0x1801a9c86  xor     r8d, r8d; unsigned __int8 *
0x1801a9c89  mov     rcx, rdi; this
0x1801a9c8c  lea     edx, [r9+0Ah]; unsigned int
0x1801a9c90  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1801a9c95  mov     ebx, eax
0x1801a9c97  test    eax, eax
0x1801a9c99  jns     short loc_1801A9CA7
0x1801a9c9b  mov     [rbp+var_4C], 93Bh
0x1801a9ca2  jmp     loc_1801A9BA1
0x1801a9ca7  mov     rdx, [rdi+20h]; tableid
0x1801a9cab  xor     r9d, r9d; cbBookmark
0x1801a9cae  mov     rcx, [rdi+10h]; sesid
0x1801a9cb2  xor     r8d, r8d; pvBookmark
0x1801a9cb5  mov     [rsp+80h+pcbActual], 0; pcbActual
0x1801a9cbe  call    cs:__imp_JetUpdate
0x1801a9cc4  mov     ecx, eax; int
0x1801a9cc6  mov     edx, esi; int
0x1801a9cc8  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9ccd  mov     ebx, eax
0x1801a9ccf  test    eax, eax
0x1801a9cd1  js      loc_1801A9BA1
0x1801a9cd7  mov     rcx, [rdi+10h]; sesid
0x1801a9cdb  mov     edx, esi; grbit
0x1801a9cdd  call    cs:__imp_JetCommitTransaction
0x1801a9ce3  mov     ecx, eax; int
0x1801a9ce5  mov     edx, esi; int
0x1801a9ce7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a9cec  mov     ebx, eax
0x1801a9cee  test    eax, eax
0x1801a9cf0  jns     loc_1801A9BC1
0x1801a9cf6  jmp     loc_1801A9BB5
```
