# CWdsMetadataStoreManagementClient::RegisterKnownObjectsOfType(_GUID *,ulong,ushort const *)

- ea: `0x180013030`
- end: `0x180013169`
- name: `?RegisterKnownObjectsOfType@CWdsMetadataStoreManagementClient@@QEAAKPEAU_GUID@@KPEBG@Z`
- size: `313`
- prototype: `unsigned int(CWdsMetadataStoreManagementClient *__hidden this, struct _GUID *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180009490`

## callees

- `0x180011e48`
- `0x1800121ac`
- `0x180012214`
- `0x180013030`
- `0x1800132c4`
- `0x180013adc`
- `0x180016020`
- `0x180017010`

## string_xrefs

- `0x1800130e4`: `InstallImage`

## pseudocode

```c
__int64 __fastcall CWdsMetadataStoreManagementClient::RegisterKnownObjectsOfType(
        __int64 (__fastcall **this)(__int128 *, __int128 *),
        struct _GUID *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int128 v19; // [rsp+30h] [rbp-50h] BYREF
  __int64 v20; // [rsp+40h] [rbp-40h]
  int v21; // [rsp+48h] [rbp-38h]
  __int128 v22; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+60h] [rbp-20h]
  int v24; // [rsp+68h] [rbp-18h]

  v20 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v19 = 0;
  v22 = 0;
  v7 = CControlPacket::SendInitialize((CControlPacket *)&v19, 0, 7u, 2u);
  if ( !(unsigned int)ElValidateWin32_7(v7, v8, v9, 0x186u) )
  {
    v7 = CControlPacket::SendInitialize((CControlPacket *)&v22, 0, 0, 2u);
    if ( !(unsigned int)ElValidateWin32_7(v7, v10, v11, 0x189u) )
    {
      v7 = CWdsMetadataStorePacket::AddObjectList((CWdsMetadataStorePacket *)&v19, a2, a3);
      if ( !(unsigned int)ElValidateWin32_7(v7, v12, v13, 0x18Cu) )
      {
        v7 = CControlPacket::AddString((CControlPacket *)&v19, L"T", 0, 0xFFFFFFFF, L"InstallImage");
        if ( !(unsigned int)ElValidateWin32_7(v7, v14, v15, 0x18Fu) )
        {
          v7 = this[1](&v19, &v22);
          ElValidateWin32_7(v7, v16, v17, 0x192u);
        }
      }
    }
  }
  CControlPacket::Shutdown((CControlPacket *)&v22);
  CControlPacket::Shutdown((CControlPacket *)&v19);
  return v7;
}

```

## disassembly

```asm
0x180013030  push    rbp
0x180013032  push    rbx
0x180013033  push    rsi
0x180013034  push    rdi
0x180013035  push    r14
0x180013037  mov     rbp, rsp
0x18001303a  sub     rsp, 80h
0x180013041  mov     rax, cs:__security_cookie
0x180013048  xor     rax, rsp
0x18001304b  mov     [rbp+var_10], rax
0x18001304f  xor     eax, eax
0x180013051  xorps   xmm0, xmm0
0x180013054  mov     esi, r8d
0x180013057  mov     [rbp+var_40], rax
0x18001305b  mov     rdi, rdx
0x18001305e  mov     [rbp+var_38], eax
0x180013061  mov     r14, rcx
0x180013064  mov     [rbp+var_20], rax
0x180013068  lea     r8d, [rax+7]; unsigned int
0x18001306c  mov     [rbp+var_18], eax
0x18001306f  mov     r9b, 2; unsigned __int8
0x180013072  lea     rcx, [rbp+var_50]; this
0x180013076  xor     edx, edx; void *
0x180013078  movdqu  [rbp+var_50], xmm0
0x18001307d  movdqu  [rbp+var_30], xmm0
0x180013082  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z; CControlPacket::SendInitialize(void *,ulong,uchar)
0x180013087  mov     r9d, 186h
0x18001308d  mov     ecx, eax
0x18001308f  mov     ebx, eax
0x180013091  call    ElValidateWin32_7
0x180013096  test    eax, eax
0x180013098  jnz     loc_18001313A
0x18001309e  mov     r9b, 2; unsigned __int8
0x1800130a1  lea     rcx, [rbp+var_30]; this
0x1800130a5  xor     r8d, r8d; unsigned int
0x1800130a8  xor     edx, edx; void *
0x1800130aa  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z; CControlPacket::SendInitialize(void *,ulong,uchar)
0x1800130af  mov     r9d, 189h
0x1800130b5  mov     ecx, eax
0x1800130b7  mov     ebx, eax
0x1800130b9  call    ElValidateWin32_7
0x1800130be  test    eax, eax
0x1800130c0  jnz     short loc_18001313A
0x1800130c2  mov     r8d, esi; unsigned int
0x1800130c5  lea     rcx, [rbp+var_50]; this
0x1800130c9  mov     rdx, rdi; struct _GUID *
0x1800130cc  call    ?AddObjectList@CWdsMetadataStorePacket@@QEAAKPEAU_GUID@@K@Z; CWdsMetadataStorePacket::AddObjectList(_GUID *,ulong)
0x1800130d1  mov     r9d, 18Ch
0x1800130d7  mov     ecx, eax
0x1800130d9  mov     ebx, eax
0x1800130db  call    ElValidateWin32_7
0x1800130e0  test    eax, eax
0x1800130e2  jnz     short loc_18001313A
0x1800130e4  lea     rax, aInstallimage; "InstallImage"
0x1800130eb  or      r9d, 0FFFFFFFFh; unsigned int
0x1800130ef  xor     r8d, r8d; unsigned __int16 *
0x1800130f2  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800130f7  lea     rdx, aT; "T"
0x1800130fe  lea     rcx, [rbp+var_50]; this
0x180013102  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x180013107  mov     r9d, 18Fh
0x18001310d  mov     ecx, eax
0x18001310f  mov     ebx, eax
0x180013111  call    ElValidateWin32_7
0x180013116  test    eax, eax
0x180013118  jnz     short loc_18001313A
0x18001311a  mov     rax, [r14+8]
0x18001311e  lea     rdx, [rbp+var_30]
0x180013122  lea     rcx, [rbp+var_50]
0x180013126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001312b  mov     r9d, 192h
0x180013131  mov     ecx, eax
0x180013133  mov     ebx, eax
0x180013135  call    ElValidateWin32_7
0x18001313a  lea     rcx, [rbp+var_30]; this
0x18001313e  call    ?Shutdown@CControlPacket@@QEAAKXZ; CControlPacket::Shutdown(void)
0x180013143  lea     rcx, [rbp+var_50]; this
0x180013147  call    ?Shutdown@CControlPacket@@QEAAKXZ; CControlPacket::Shutdown(void)
0x18001314c  mov     eax, ebx
0x18001314e  mov     rcx, [rbp+var_10]
0x180013152  xor     rcx, rsp; StackCookie
0x180013155  call    __security_check_cookie
0x18001315a  add     rsp, 80h
0x180013161  pop     r14
0x180013163  pop     rdi
0x180013164  pop     rsi
0x180013165  pop     rbx
0x180013166  pop     rbp
0x180013167  retn
```
