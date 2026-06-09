# MakeRsaSessionKeysHelper(CSsl3TlsContext *,unsigned __int64)

- ea: `0x18004db0c`
- end: `0x18004dd72`
- name: `?MakeRsaSessionKeysHelper@@YAKPEAVCSsl3TlsContext@@_K@Z`
- size: `614`
- prototype: `unsigned int __fastcall(struct CSsl3TlsContext *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001aecc`

## callees

- `0x180003e60`
- `0x180011054`
- `0x1800214f0`
- `0x18004db0c`
- `0x1800597b0`
- `0x18005a160`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18004dd18`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004dd18`
- `ntdll!RtlReleaseResource` at `0x18004dd36`
- `ntdll!RtlReleaseResource` at `0x18004dd36`
- `ncrypt!SslComputeSessionHash` at `0x18004dbdb`
- `ncrypt!SslComputeSessionHash` at `0x18004dbdb`
- `ncrypt!SslFreeObject` at `0x18004dcff`
- `ncrypt!SslFreeObject` at `0x18004dcff`
- `ncrypt!SslGenerateMasterKey` at `0x18004dcb3`
- `ncrypt!SslGenerateMasterKey` at `0x18004dcb3`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18004dd44`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18004dd44`

## pseudocode

```c
__int64 __fastcall MakeRsaSessionKeysHelper(struct CSsl3TlsContext *this, __int64 a2)
{
  unsigned int v5; // edi
  __int64 v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rcx
  unsigned int SessionKeys; // edi
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  struct CSsl3TlsContext *v13; // rcx
  __int64 v14; // rax
  int v15; // edx
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int64 v21; // [rsp+68h] [rbp-41h] BYREF
  __int128 v22; // [rsp+70h] [rbp-39h] BYREF
  __int128 v23; // [rsp+80h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v25[64]; // [rsp+A0h] [rbp-9h] BYREF

  v21 = 0;
  LODWORD(v22) = 0;
  memset((char *)&v22 + 4, 0, 12);
  v23 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  if ( !this )
    return 87;
  if ( (*((_DWORD *)this + 22) & 0xA2A80) == 0 || (*((_DWORD *)this + 464) & 0x8000000) == 0 )
    return 1359;
  v5 = *((unsigned __int16 *)this + 17);
  v6 = (*(__int64 (__fastcall **)(struct CSsl3TlsContext *, _QWORD))(*(_QWORD *)this + 576LL))(this, 0);
  v7 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v7 )
    v7 = (_QWORD *)*v7;
  SessionKeys = SslComputeSessionHash(v7, v6, v5, v25, 64, &v20, 0);
  if ( SessionKeys )
  {
    v12 = 604;
    v13 = this;
LABEL_9:
    LOBYTE(v11) = 51;
    CSslContext::SetErrorAndFatalAlert(v13, v12, SessionKeys, v11);
    return SessionKeys;
  }
  *((_QWORD *)&v23 + 1) = &v22;
  *(_QWORD *)&v22 = v20 | 0x1900000000LL;
  *((_QWORD *)&v22 + 1) = v25;
  *(_QWORD *)&v23 = 0x100000000LL;
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)&GenerateMasterKeyStart, v10, v11, &v24);
  if ( (*((_BYTE *)this + 32) & 1) != 0 && (v14 = *((_QWORD *)this + 1)) != 0 )
    v15 = *(_DWORD *)(v14 + 28);
  else
    v15 = 0;
  v16 = (__int64 *)*((_QWORD *)this + 1);
  if ( v16 )
    v17 = *v16;
  else
    v17 = 0;
  SessionKeys = SslGenerateMasterKey(v17, a2, 0, &v21, *((unsigned __int16 *)this + 17), v15, &v23, 0, 0, &v20, 1);
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v18, (const EVENT_DESCRIPTOR *)&GenerateMasterKeyStop, v19, v11, &v24);
  v13 = this;
  if ( SessionKeys )
  {
    v12 = 706;
    goto LABEL_9;
  }
  SessionKeys = CSslContext::MakeSessionKeys(this, v21);
  if ( SessionKeys )
  {
    SslFreeObject(v21, 0);
    return SessionKeys;
  }
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL), 1u);
  *(_QWORD *)(*((_QWORD *)this + 14) + 32LL) = v21;
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL));
  LsaIModifyPerformanceCounter(6, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18004db0c  mov     [rsp-8+arg_10], rbx
0x18004db11  push    rbp
0x18004db12  push    rsi
0x18004db13  push    rdi
0x18004db14  lea     rbp, [rsp-47h]
0x18004db19  sub     rsp, 0F0h
0x18004db20  mov     rax, cs:__security_cookie
0x18004db27  xor     rax, rsp
0x18004db2a  mov     [rbp+57h+var_20], rax
0x18004db2e  xor     eax, eax
0x18004db30  mov     [rbp+57h+var_98], 0
0x18004db38  mov     rsi, rdx
0x18004db3b  mov     [rbp+57h+var_90], 0
0x18004db42  mov     rbx, rcx
0x18004db45  mov     [rbp+57h+var_8C], rax
0x18004db49  xorps   xmm0, xmm0
0x18004db4c  mov     [rbp+57h+var_84], eax
0x18004db4f  lea     r8d, [rax+40h]; Size
0x18004db53  xor     edx, edx; Val
0x18004db55  lea     rcx, [rbp+57h+var_60]; void *
0x18004db59  movups  [rbp+57h+var_80], xmm0
0x18004db5d  call    memset_0
0x18004db62  mov     [rbp+57h+var_A0], 0
0x18004db69  test    rbx, rbx
0x18004db6c  jnz     short loc_18004DB76
0x18004db6e  lea     eax, [rbx+57h]
0x18004db71  jmp     loc_18004DD53
0x18004db76  test    dword ptr [rbx+58h], 0A2A80h
0x18004db7d  jz      loc_18004DD4E
0x18004db83  mov     eax, [rbx+740h]
0x18004db89  bt      rax, 1Bh
0x18004db8e  jnb     loc_18004DD4E
0x18004db94  mov     rax, [rbx]
0x18004db97  xor     edx, edx
0x18004db99  movzx   edi, word ptr [rbx+22h]
0x18004db9d  mov     rcx, rbx
0x18004dba0  mov     rax, [rax+240h]
0x18004dba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbac  mov     rcx, [rbx+8]
0x18004dbb0  test    rcx, rcx
0x18004dbb3  jz      short loc_18004DBB8
0x18004dbb5  mov     rcx, [rcx]
0x18004dbb8  lea     rdx, [rbp+57h+var_A0]
0x18004dbbc  mov     dword ptr [rsp+100h+var_D0], 0
0x18004dbc4  mov     [rsp+100h+var_D8], rdx
0x18004dbc9  lea     r9, [rbp+57h+var_60]
0x18004dbcd  mov     rdx, rax
0x18004dbd0  mov     dword ptr [rsp+100h+var_E0], 40h ; '@'
0x18004dbd8  mov     r8d, edi
0x18004dbdb  call    cs:__imp_SslComputeSessionHash
0x18004dbe1  mov     edi, eax
0x18004dbe3  test    eax, eax
0x18004dbe5  jz      short loc_18004DC01
0x18004dbe7  mov     edx, 25Ch
0x18004dbec  mov     rcx, rbx
0x18004dbef  mov     r8d, edi
0x18004dbf2  mov     r9b, 33h ; '3'
0x18004dbf5  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18004dbfa  mov     eax, edi
0x18004dbfc  jmp     loc_18004DD53
0x18004dc01  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18004dc08  lea     rax, [rbp+57h+var_90]
0x18004dc0c  mov     qword ptr [rbp+57h+var_80+8], rax
0x18004dc10  mov     eax, [rbp+57h+var_A0]
0x18004dc13  mov     [rbp+57h+var_90], eax
0x18004dc16  lea     rax, [rbp+57h+var_60]
0x18004dc1a  mov     [rbp+57h+var_8C+4], rax
0x18004dc1e  mov     dword ptr [rbp+57h+var_80], 0
0x18004dc25  mov     dword ptr [rbp+57h+var_80+4], 1
0x18004dc2c  mov     dword ptr [rbp+57h+var_8C], 19h
0x18004dc33  jz      short loc_18004DC4A
0x18004dc35  lea     rax, [rbp+57h+var_70]
0x18004dc39  lea     rdx, GenerateMasterKeyStart; int
0x18004dc40  mov     [rsp+100h+var_E0], rax; PEVENT_DATA_DESCRIPTOR
0x18004dc45  call    McGenEventWrite_EventWriteTransfer
0x18004dc4a  test    byte ptr [rbx+20h], 1
0x18004dc4e  jz      short loc_18004DC5E
0x18004dc50  mov     rax, [rbx+8]
0x18004dc54  test    rax, rax
0x18004dc57  jz      short loc_18004DC5E
0x18004dc59  mov     edx, [rax+1Ch]
0x18004dc5c  jmp     short loc_18004DC60
0x18004dc5e  xor     edx, edx
0x18004dc60  mov     rax, [rbx+8]
0x18004dc64  movzx   r8d, word ptr [rbx+22h]
0x18004dc69  test    rax, rax
0x18004dc6c  jz      short loc_18004DC73
0x18004dc6e  mov     rcx, [rax]
0x18004dc71  jmp     short loc_18004DC75
0x18004dc73  xor     ecx, ecx
0x18004dc75  mov     [rsp+100h+var_B0], 1
0x18004dc7d  lea     rax, [rbp+57h+var_A0]
0x18004dc81  mov     [rsp+100h+var_B8], rax
0x18004dc86  lea     r9, [rbp+57h+var_98]
0x18004dc8a  mov     [rsp+100h+var_C0], 0
0x18004dc92  lea     rax, [rbp+57h+var_80]
0x18004dc96  mov     [rsp+100h+var_C8], 0
0x18004dc9f  mov     [rsp+100h+var_D0], rax
0x18004dca4  mov     dword ptr [rsp+100h+var_D8], edx
0x18004dca8  mov     rdx, rsi
0x18004dcab  mov     dword ptr [rsp+100h+var_E0], r8d
0x18004dcb0  xor     r8d, r8d
0x18004dcb3  call    cs:__imp_SslGenerateMasterKey
0x18004dcb9  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18004dcc0  mov     edi, eax
0x18004dcc2  jz      short loc_18004DCD9
0x18004dcc4  lea     rax, [rbp+57h+var_70]
0x18004dcc8  lea     rdx, GenerateMasterKeyStop; int
0x18004dccf  mov     [rsp+100h+var_E0], rax; PEVENT_DATA_DESCRIPTOR
0x18004dcd4  call    McGenEventWrite_EventWriteTransfer
0x18004dcd9  mov     rcx, rbx; this
0x18004dcdc  test    edi, edi
0x18004dcde  jz      short loc_18004DCEA
0x18004dce0  mov     edx, 2C2h
0x18004dce5  jmp     loc_18004DBEF
0x18004dcea  mov     rdx, [rbp+57h+var_98]; unsigned __int64
0x18004dcee  call    ?MakeSessionKeys@CSslContext@@QEAAK_K@Z; CSslContext::MakeSessionKeys(unsigned __int64)
0x18004dcf3  mov     edi, eax
0x18004dcf5  test    eax, eax
0x18004dcf7  jz      short loc_18004DD0A
0x18004dcf9  mov     rcx, [rbp+57h+var_98]
0x18004dcfd  xor     edx, edx
0x18004dcff  call    cs:__imp_SslFreeObject
0x18004dd05  jmp     loc_18004DBFA
0x18004dd0a  mov     rax, [rbx+70h]
0x18004dd0e  mov     dl, 1; Wait
0x18004dd10  mov     rcx, [rax+28h]
0x18004dd14  add     rcx, 50h ; 'P'; Resource
0x18004dd18  call    cs:__imp_RtlAcquireResourceExclusive
0x18004dd1e  mov     rcx, [rbx+70h]
0x18004dd22  mov     rax, [rbp+57h+var_98]
0x18004dd26  mov     [rcx+20h], rax
0x18004dd2a  mov     rax, [rbx+70h]
0x18004dd2e  mov     rcx, [rax+28h]
0x18004dd32  add     rcx, 50h ; 'P'; Resource
0x18004dd36  call    cs:__imp_RtlReleaseResource
0x18004dd3c  xor     edx, edx
0x18004dd3e  xor     r8d, r8d
0x18004dd41  lea     ecx, [rdx+6]
0x18004dd44  call    cs:__imp_LsaIModifyPerformanceCounter
0x18004dd4a  xor     eax, eax
0x18004dd4c  jmp     short loc_18004DD53
0x18004dd4e  mov     eax, 54Fh
0x18004dd53  mov     rcx, [rbp+57h+var_20]
0x18004dd57  xor     rcx, rsp; StackCookie
0x18004dd5a  call    __security_check_cookie
0x18004dd5f  mov     rbx, [rsp+100h+arg_10]
0x18004dd67  add     rsp, 0F0h
0x18004dd6e  pop     rdi
0x18004dd6f  pop     rsi
0x18004dd70  pop     rbp
0x18004dd71  retn
```
