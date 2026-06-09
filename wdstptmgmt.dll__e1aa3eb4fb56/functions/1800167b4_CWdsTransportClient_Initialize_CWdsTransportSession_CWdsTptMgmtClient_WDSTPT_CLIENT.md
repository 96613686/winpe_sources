# CWdsTransportClient::Initialize(CWdsTransportSession *,CWdsTptMgmtClient *,_WDSTPT_CLIENT *)

- ea: `0x1800167b4`
- end: `0x180016a9d`
- name: `?Initialize@CWdsTransportClient@@AEAAJPEAVCWdsTransportSession@@PEAVCWdsTptMgmtClient@@PEAU_WDSTPT_CLIENT@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(CWdsTransportClient *__hidden this, struct CWdsTransportSession *, struct CWdsTptMgmtClient *, struct _WDSTPT_CLIENT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800163b8`

## callees

- `0x1800167b4`
- `0x180016f20`
- `0x180017044`
- `0x180020010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180016a41`
- `KERNEL32!LocalFree` at `0x180016a41`
- `KERNEL32!GetLastError` at `0x18001697a`
- `KERNEL32!GetLastError` at `0x18001697a`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18001696a`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18001696a`
- `WdsCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x180016877`
- `WdsCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x180016877`
- `WdsCommonLib!?MacAddressToString@CNetworkAddress@@SAKUtagWDS_MAC_ADDRESS@@PEAPEAG@Z` at `0x1800168b6`
- `WdsCommonLib!?MacAddressToString@CNetworkAddress@@SAKUtagWDS_MAC_ADDRESS@@PEAPEAG@Z` at `0x1800168b6`
- `WdsCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z` at `0x18001690a`
- `WdsCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z` at `0x18001690a`
- `WdsCommonLib!?ResolveAccountSid@@YAKPEAXPEAPEAG11@Z` at `0x180016948`
- `WdsCommonLib!?ResolveAccountSid@@YAKPEAXPEAPEAG11@Z` at `0x180016948`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800169bc`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800169bc`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800167f3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016a67`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800167f3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016a67`

## pseudocode

```c
__int64 __fastcall CWdsTransportClient::Initialize(
        CWdsTransportClient *this,
        struct CWdsTransportSession *a2,
        struct CWdsTptMgmtClient *a3,
        struct _WDSTPT_CLIENT *a4)
{
  __int64 v8; // rbx
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int128 v12; // xmm0
  __int64 v13; // rbp
  __int64 v14; // rdx
  __int64 v15; // r8
  __int128 v16; // xmm0
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  DWORD LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r9
  char v27; // dl
  char v28; // al
  char v29; // cl
  char v30; // al
  __int128 v32; // [rsp+30h] [rbp-38h] BYREF
  int v33; // [rsp+40h] [rbp-28h]
  LPWSTR StringSid; // [rsp+70h] [rbp+8h] BYREF

  StringSid = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportClient::Initialize(0x%p)", this);
  if ( *((_DWORD *)this + 30) )
  {
    LODWORD(v8) = -1055915767;
    goto LABEL_27;
  }
  *((_QWORD *)this + 13) = a2;
  (*(void (__fastcall **)(struct CWdsTransportSession *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_QWORD *)this + 14) = a3;
  (**(void (__fastcall ***)(struct CWdsTptMgmtClient *))a3)(a3);
  v9 = (const unsigned __int16 *)&dword_18002BACC;
  *((_QWORD *)this + 16) = *(_QWORD *)a4;
  *((_QWORD *)this + 17) = *((_QWORD *)a4 + 1);
  *((_QWORD *)this + 18) = *((_QWORD *)a4 + 2);
  *((_QWORD *)this + 19) = *((_QWORD *)a4 + 3);
  if ( *((_QWORD *)a4 + 4) )
    v9 = (const unsigned __int16 *)*((_QWORD *)a4 + 4);
  v8 = (unsigned int)WcsDupHr(v9, (unsigned __int16 **)this + 20);
  if ( (int)ElValidateHr_11(v8, v10, v11, 201) >= 0 )
  {
    v12 = *(_OWORD *)((char *)a4 + 40);
    v33 = *((_DWORD *)a4 + 14);
    v32 = v12;
    v13 = (unsigned int)CNetworkAddress::MacAddressToString(&v32, (char *)this + 168);
    if ( (unsigned int)ElValidateWin32_10(v13, v14, v15, 205) )
      goto LABEL_7;
    v16 = *(_OWORD *)((char *)a4 + 60);
    v33 = *((_DWORD *)a4 + 19);
    v32 = v16;
    v13 = (unsigned int)CNetworkAddress::IpAddressToString(&v32, (char *)this + 176);
    if ( (unsigned int)ElValidateWin32_10(v13, v17, v18, 209) )
      goto LABEL_7;
    if ( *((_DWORD *)a4 + 534) )
    {
      LODWORD(v13) = ResolveAccountSid((char *)a4 + 88, 0, 0, (unsigned __int16 **)this + 23);
      if ( (_DWORD)v13 == 1332 )
      {
        if ( !ConvertSidToStringSidW((char *)a4 + 88, &StringSid) )
        {
          LastError = GetLastError();
          v24 = ElValidateWin32_10(LastError, v22, v23, 231);
          LODWORD(v8) = v24;
          if ( v24 > 0 )
            LODWORD(v8) = (unsigned __int16)v24 | 0x80070000;
          if ( (int)v8 >= 0 )
            LODWORD(v8) = -2147467259;
          goto LABEL_27;
        }
        v13 = DuplicateStringW(StringSid, (unsigned __int16 **)this + 23);
        v25 = v13;
        v26 = 240;
      }
      else
      {
        v26 = 247;
        v25 = (unsigned int)v13;
      }
      if ( (unsigned int)ElValidateWin32_10(v25, v19, v20, v26) )
      {
LABEL_7:
        if ( (int)v13 > 0 )
          LODWORD(v8) = (unsigned __int16)v13 | 0x80070000;
        else
          LODWORD(v8) = v13;
        goto LABEL_27;
      }
    }
    v27 = -1;
    *((_DWORD *)this + 48) = *((_DWORD *)a4 + 20);
    *((_DWORD *)this + 49) = *((_DWORD *)a4 + 21);
    v28 = -1;
    if ( *((_BYTE *)a4 + 2140) != 0xFF )
      v28 = *((_BYTE *)a4 + 2140);
    v29 = -1;
    *((_BYTE *)this + 200) = v28;
    if ( *((_BYTE *)a4 + 2141) != 0xFF )
      v29 = *((_BYTE *)a4 + 2141);
    *((_BYTE *)this + 201) = v29;
    v30 = *((_BYTE *)a4 + 2142);
    *((_DWORD *)this + 30) = 1;
    if ( v30 != -1 )
      v27 = v30;
    *((_BYTE *)this + 202) = v27;
  }
LABEL_27:
  if ( StringSid )
    LocalFree(StringSid);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportClient::Initialize(0x%p) =%x", this, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800167b4  mov     rax, rsp
0x1800167b7  mov     [rax+10h], rbx
0x1800167bb  mov     [rax+18h], rbp
0x1800167bf  mov     [rax+20h], rsi
0x1800167c3  push    rdi
0x1800167c4  push    r14
0x1800167c6  push    r15
0x1800167c8  sub     rsp, 50h
0x1800167cc  and     qword ptr [rax+8], 0
0x1800167d1  mov     rsi, r9
0x1800167d4  mov     r9, rcx
0x1800167d7  mov     rbx, r8
0x1800167da  mov     r14, rdx
0x1800167dd  lea     r8, aCwdstransportc_23; "-> CWdsTransportClient::Initialize(0x%p"...
0x1800167e4  mov     rdi, rcx
0x1800167e7  mov     edx, 10000h
0x1800167ec  lea     rcx, qword_18003B770
0x1800167f3  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800167fa  nop     dword ptr [rax+rax+00h]
0x1800167ff  cmp     dword ptr [rdi+78h], 0
0x180016803  jz      short loc_18001680F
0x180016805  mov     ebx, 0C1100109h
0x18001680a  jmp     loc_180016A37
0x18001680f  mov     [rdi+68h], r14
0x180016813  mov     rcx, r14
0x180016816  mov     rax, [r14]
0x180016819  mov     rax, [rax+8]
0x18001681d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016822  mov     [rdi+70h], rbx
0x180016826  mov     rcx, rbx
0x180016829  mov     rax, [rbx]
0x18001682c  mov     rax, [rax]
0x18001682f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016834  mov     rax, [rsi]
0x180016837  lea     rcx, dword_18002BACC
0x18001683e  mov     [rdi+80h], rax
0x180016845  lea     rdx, [rdi+0A0h]
0x18001684c  mov     rax, [rsi+8]
0x180016850  mov     [rdi+88h], rax
0x180016857  mov     rax, [rsi+10h]
0x18001685b  mov     [rdi+90h], rax
0x180016862  mov     rax, [rsi+18h]
0x180016866  mov     [rdi+98h], rax
0x18001686d  cmp     qword ptr [rsi+20h], 0
0x180016872  cmovnz  rcx, [rsi+20h]
0x180016877  call    cs:__imp_?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x18001687e  nop     dword ptr [rax+rax+00h]
0x180016883  mov     ecx, eax
0x180016885  mov     r9d, 0C9h
0x18001688b  mov     ebx, eax
0x18001688d  call    ElValidateHr_11
0x180016892  test    eax, eax
0x180016894  js      loc_180016A37
0x18001689a  mov     ecx, [rsi+38h]
0x18001689d  lea     rdx, [rdi+0A8h]
0x1800168a4  movups  xmm0, xmmword ptr [rsi+28h]
0x1800168a8  mov     [rsp+68h+var_28], ecx
0x1800168ac  lea     rcx, [rsp+68h+var_38]
0x1800168b1  movaps  [rsp+68h+var_38], xmm0
0x1800168b6  call    cs:__imp_?MacAddressToString@CNetworkAddress@@SAKUtagWDS_MAC_ADDRESS@@PEAPEAG@Z; CNetworkAddress::MacAddressToString(tagWDS_MAC_ADDRESS,ushort * *)
0x1800168bd  nop     dword ptr [rax+rax+00h]
0x1800168c2  mov     ecx, eax
0x1800168c4  mov     r9d, 0CDh
0x1800168ca  mov     ebp, eax
0x1800168cc  call    ElValidateWin32_10
0x1800168d1  test    eax, eax
0x1800168d3  jz      short loc_1800168EE
0x1800168d5  test    ebp, ebp
0x1800168d7  jg      short loc_1800168E0
0x1800168d9  mov     ebx, ebp
0x1800168db  jmp     loc_180016A37
0x1800168e0  movzx   ebx, bp
0x1800168e3  or      ebx, 80070000h
0x1800168e9  jmp     loc_180016A37
0x1800168ee  movups  xmm0, xmmword ptr [rsi+3Ch]
0x1800168f2  mov     eax, [rsi+4Ch]
0x1800168f5  lea     rdx, [rdi+0B0h]
0x1800168fc  lea     rcx, [rsp+68h+var_38]
0x180016901  mov     [rsp+68h+var_28], eax
0x180016905  movaps  [rsp+68h+var_38], xmm0
0x18001690a  call    cs:__imp_?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z; CNetworkAddress::IpAddressToString(tagWDS_IP_ADDRESS6,ushort * *)
0x180016911  nop     dword ptr [rax+rax+00h]
0x180016916  mov     ecx, eax
0x180016918  mov     r9d, 0D1h
0x18001691e  mov     ebp, eax
0x180016920  call    ElValidateWin32_10
0x180016925  test    eax, eax
0x180016927  jnz     short loc_1800168D5
0x180016929  cmp     [rsi+858h], eax
0x18001692f  jbe     loc_1800169DF
0x180016935  lea     r15, [rdi+0B8h]
0x18001693c  xor     r8d, r8d
0x18001693f  mov     r9, r15
0x180016942  lea     rcx, [rsi+58h]
0x180016946  xor     edx, edx
0x180016948  call    cs:__imp_?ResolveAccountSid@@YAKPEAXPEAPEAG11@Z; ResolveAccountSid(void *,ushort * *,ushort * *,ushort * *)
0x18001694f  nop     dword ptr [rax+rax+00h]
0x180016954  mov     ebp, eax
0x180016956  cmp     eax, 534h
0x18001695b  jnz     loc_180016A90
0x180016961  lea     rdx, [rsp+68h+StringSid]; StringSid
0x180016966  lea     rcx, [rsi+58h]; Sid
0x18001696a  call    cs:__imp_ConvertSidToStringSidW
0x180016971  nop     dword ptr [rax+rax+00h]
0x180016976  test    eax, eax
0x180016978  jnz     short loc_1800169B4
0x18001697a  call    cs:__imp_GetLastError
0x180016981  nop     dword ptr [rax+rax+00h]
0x180016986  mov     ecx, eax
0x180016988  mov     r9d, 0E7h
0x18001698e  call    ElValidateWin32_10
0x180016993  mov     ebx, eax
0x180016995  test    eax, eax
0x180016997  jle     short loc_1800169A2
0x180016999  movzx   ebx, ax
0x18001699c  or      ebx, 80070000h
0x1800169a2  test    ebx, ebx
0x1800169a4  js      loc_180016A37
0x1800169aa  mov     ebx, 80004005h
0x1800169af  jmp     loc_180016A37
0x1800169b4  mov     rcx, [rsp+68h+StringSid]
0x1800169b9  mov     rdx, r15
0x1800169bc  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800169c3  nop     dword ptr [rax+rax+00h]
0x1800169c8  mov     ebp, eax
0x1800169ca  mov     ecx, eax
0x1800169cc  mov     r9d, 0F0h
0x1800169d2  call    ElValidateWin32_10
0x1800169d7  test    eax, eax
0x1800169d9  jnz     loc_1800168D5
0x1800169df  mov     eax, [rsi+50h]
0x1800169e2  mov     edx, 0FFh
0x1800169e7  mov     [rdi+0C0h], eax
0x1800169ed  mov     eax, [rsi+54h]
0x1800169f0  mov     [rdi+0C4h], eax
0x1800169f6  mov     eax, edx
0x1800169f8  movzx   ecx, byte ptr [rsi+85Ch]
0x1800169ff  cmp     cl, dl
0x180016a01  cmovnz  eax, ecx
0x180016a04  mov     ecx, edx
0x180016a06  mov     [rdi+0C8h], al
0x180016a0c  movzx   eax, byte ptr [rsi+85Dh]
0x180016a13  cmp     al, dl
0x180016a15  cmovnz  ecx, eax
0x180016a18  mov     [rdi+0C9h], cl
0x180016a1e  movzx   eax, byte ptr [rsi+85Eh]
0x180016a25  cmp     al, dl
0x180016a27  mov     dword ptr [rdi+78h], 1
0x180016a2e  cmovnz  edx, eax
0x180016a31  mov     [rdi+0CAh], dl
0x180016a37  mov     rcx, [rsp+68h+StringSid]; hMem
0x180016a3c  test    rcx, rcx
0x180016a3f  jz      short loc_180016A4D
0x180016a41  call    cs:__imp_LocalFree
0x180016a48  nop     dword ptr [rax+rax+00h]
0x180016a4d  mov     r9, rdi
0x180016a50  mov     [rsp+68h+var_48], ebx
0x180016a54  lea     r8, aCwdstransportc_8; "<- CWdsTransportClient::Initialize(0x%p"...
0x180016a5b  mov     edx, 10000h
0x180016a60  lea     rcx, qword_18003B770
0x180016a67  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180016a6e  nop     dword ptr [rax+rax+00h]
0x180016a73  lea     r11, [rsp+68h+var_18]
0x180016a78  mov     eax, ebx
0x180016a7a  mov     rbx, [r11+28h]
0x180016a7e  mov     rbp, [r11+30h]
0x180016a82  mov     rsi, [r11+38h]
0x180016a86  mov     rsp, r11
0x180016a89  pop     r15
0x180016a8b  pop     r14
0x180016a8d  pop     rdi
0x180016a8e  retn
0x180016a90  mov     r9d, 0F7h
0x180016a96  mov     ecx, ebp
0x180016a98  jmp     loc_1800169D2
```
