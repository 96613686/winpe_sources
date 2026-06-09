# CRegUdpEndpoint::DumpState(void)

- ea: `0x180014850`
- end: `0x180014a59`
- name: `?DumpState@CRegUdpEndpoint@@UEAAXXZ`
- size: `521`
- prototype: `void __fastcall(CRegUdpEndpoint *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180014850`
- `0x18001c112`
- `0x18001c150`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180014a28`
- `KERNEL32!LeaveCriticalSection` at `0x180014a28`
- `KERNEL32!EnterCriticalSection` at `0x180014885`
- `KERNEL32!EnterCriticalSection` at `0x180014885`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800148d9`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014a10`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800148d9`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014a10`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z` at `0x1800149c7`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z` at `0x1800149c7`

## string_xrefs

- `0x1800148ce`: `Udp Endpoint\n------------\nRegistered By: %s\nLocal Udp Port: %u\nActive Requests: %u\nPending Close: %s\n\nEndpoint opened on following interfaces:`

## pseudocode

```c
void __fastcall CRegUdpEndpoint::DumpState(CRegUdpEndpoint *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  const wchar_t *v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rcx
  char *v6; // rdx
  __int128 *v7; // rcx
  __int64 v8; // rax
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int64 v17; // rax
  __int128 v18; // xmm0
  bool v19; // zf
  const wchar_t *v20; // r9
  __int64 v21; // [rsp+20h] [rbp-E0h]
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+50h] [rbp-B0h]
  char v24; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25; // [rsp+6Ch] [rbp-94h]
  _BYTE Src[16]; // [rsp+70h] [rbp-90h] BYREF
  size_t Size; // [rsp+80h] [rbp-80h]
  __int128 v28; // [rsp+480h] [rbp+380h] BYREF
  int v29; // [rsp+490h] [rbp+390h]
  BOOL v30; // [rsp+4A0h] [rbp+3A0h]
  _BYTE v31[140]; // [rsp+4A4h] [rbp+3A4h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = L"Yes";
  if ( !*((_DWORD *)this + 15) )
    v3 = L"No";
  CTrace::Trace(
    (CTrace *)qword_180039310,
    0x20000u,
    L"Udp Endpoint\n"
     "------------\n"
     "Registered By: %s\n"
     "Local Udp Port: %u\n"
     "Active Requests: %u\n"
     "Pending Close: %s\n"
     "\n"
     "Endpoint opened on following interfaces:",
    *(_QWORD *)(*((_QWORD *)this + 8) + 16LL),
    *((unsigned __int16 *)this + 42),
    *((_DWORD *)this + 14),
    v3);
  v4 = *((_QWORD *)this + 227);
  while ( v4 )
  {
    v5 = v4;
    v6 = &v24;
    v4 = *(_QWORD *)(v4 + 2304);
    v7 = (__int128 *)(v5 + 988);
    v8 = 8;
    do
    {
      v9 = *v7;
      v10 = v7[1];
      v7 += 8;
      *(_OWORD *)v6 = v9;
      v11 = *(v7 - 6);
      *((_OWORD *)v6 + 1) = v10;
      v12 = *(v7 - 5);
      *((_OWORD *)v6 + 2) = v11;
      v13 = *(v7 - 4);
      *((_OWORD *)v6 + 3) = v12;
      v14 = *(v7 - 3);
      *((_OWORD *)v6 + 4) = v13;
      v15 = *(v7 - 2);
      *((_OWORD *)v6 + 5) = v14;
      v16 = *(v7 - 1);
      *((_OWORD *)v6 + 6) = v15;
      v6 += 128;
      *((_OWORD *)v6 - 1) = v16;
      --v8;
    }
    while ( v8 );
    v17 = *((_QWORD *)v7 + 2);
    v18 = *v7;
    v28 = 0u;
    *(_OWORD *)v6 = v18;
    *((_QWORD *)v6 + 2) = v17;
    *((_DWORD *)v6 + 6) = *((_DWORD *)v7 + 6);
    v29 = Size;
    memcpy_0(&v28, Src, (unsigned int)Size);
    v23 = v29;
    v22 = v28;
    v19 = (unsigned int)CNetworkAddress::IpAddressToString(&v22, v31, 64) == 0;
    v20 = (const wchar_t *)v31;
    LODWORD(v21) = v25;
    v30 = !v19;
    if ( !v19 )
      v20 = L"<<Failed>>";
    CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Interface: %s:%u", v20, v21);
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180014850  mov     [rsp-8+arg_8], rbx
0x180014855  mov     [rsp-8+arg_10], rdi
0x18001485a  push    rbp
0x18001485b  lea     rbp, [rsp-440h]
0x180014863  sub     rsp, 540h
0x18001486a  mov     rax, cs:__security_cookie
0x180014871  xor     rax, rsp
0x180014874  mov     [rbp+440h+var_10], rax
0x18001487b  lea     rdi, [rcx+10h]
0x18001487f  mov     rbx, rcx
0x180014882  mov     rcx, rdi; lpCriticalSection
0x180014885  call    cs:__imp_EnterCriticalSection
0x18001488c  nop     dword ptr [rax+rax+00h]
0x180014891  mov     eax, [rbx+3Ch]
0x180014894  lea     rcx, aNo; "No"
0x18001489b  mov     r8d, [rbx+38h]
0x18001489f  lea     rdx, aYes; "Yes"
0x1800148a6  mov     r9, [rbx+40h]
0x1800148aa  test    eax, eax
0x1800148ac  movzx   eax, word ptr [rbx+54h]
0x1800148b0  cmovz   rdx, rcx
0x1800148b4  lea     rcx, qword_180039310
0x1800148bb  mov     [rsp+540h+var_510], rdx
0x1800148c0  mov     edx, 20000h
0x1800148c5  mov     r9, [r9+10h]
0x1800148c9  mov     [rsp+540h+var_518], r8d
0x1800148ce  lea     r8, aUdpEndpointReg; "Udp Endpoint\n------------\nRegistered "...
0x1800148d5  mov     dword ptr [rsp+540h+var_520], eax
0x1800148d9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800148e0  nop     dword ptr [rax+rax+00h]
0x1800148e5  mov     rbx, [rbx+718h]
0x1800148ec  jmp     loc_180014A1C
0x1800148f1  mov     rcx, rbx
0x1800148f4  lea     rdx, [rsp+540h+var_4E0]
0x1800148f9  mov     rbx, [rbx+900h]
0x180014900  add     rcx, 3DCh
0x180014907  mov     eax, 8
0x18001490c  movups  xmm0, xmmword ptr [rcx]
0x18001490f  movups  xmm1, xmmword ptr [rcx+10h]
0x180014913  lea     rcx, [rcx+80h]
0x18001491a  movups  xmmword ptr [rdx], xmm0
0x18001491d  movups  xmm0, xmmword ptr [rcx-60h]
0x180014921  movups  xmmword ptr [rdx+10h], xmm1
0x180014925  movups  xmm1, xmmword ptr [rcx-50h]
0x180014929  movups  xmmword ptr [rdx+20h], xmm0
0x18001492d  movups  xmm0, xmmword ptr [rcx-40h]
0x180014931  movups  xmmword ptr [rdx+30h], xmm1
0x180014935  movups  xmm1, xmmword ptr [rcx-30h]
0x180014939  movups  xmmword ptr [rdx+40h], xmm0
0x18001493d  movups  xmm0, xmmword ptr [rcx-20h]
0x180014941  movups  xmmword ptr [rdx+50h], xmm1
0x180014945  movups  xmm1, xmmword ptr [rcx-10h]
0x180014949  movups  xmmword ptr [rdx+60h], xmm0
0x18001494d  lea     rdx, [rdx+80h]
0x180014954  movups  xmmword ptr [rdx-10h], xmm1
0x180014958  sub     rax, 1
0x18001495c  jnz     short loc_18001490C
0x18001495e  mov     rax, [rcx+10h]
0x180014962  movups  xmm0, xmmword ptr [rcx]
0x180014965  and     qword ptr [rbp+440h+var_C0], 0
0x18001496d  and     qword ptr [rbp+440h+var_C0+8], 0
0x180014975  movups  xmmword ptr [rdx], xmm0
0x180014978  mov     [rdx+10h], rax
0x18001497c  mov     eax, [rcx+18h]
0x18001497f  lea     rcx, [rbp+440h+var_C0]; void *
0x180014986  mov     [rdx+18h], eax
0x180014989  lea     rdx, [rsp+540h+Src]; Src
0x18001498e  mov     eax, dword ptr [rbp+440h+Size]
0x180014991  mov     r8d, eax; Size
0x180014994  mov     [rbp+440h+var_B0], eax
0x18001499a  call    memcpy_0
0x18001499f  movups  xmm0, [rbp+440h+var_C0]
0x1800149a6  mov     eax, [rbp+440h+var_B0]
0x1800149ac  lea     rdx, [rbp+440h+var_9C]
0x1800149b3  mov     r8d, 40h ; '@'
0x1800149b9  mov     [rsp+540h+var_4F0], eax
0x1800149bd  lea     rcx, [rsp+540h+var_500]
0x1800149c2  movaps  [rsp+540h+var_500], xmm0
0x1800149c7  call    cs:__imp_?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z; CNetworkAddress::IpAddressToString(tagWDS_IP_ADDRESS6,ushort *,ulong)
0x1800149ce  nop     dword ptr [rax+rax+00h]
0x1800149d3  xor     edx, edx
0x1800149d5  lea     rcx, aFailed_0; "<<Failed>>"
0x1800149dc  test    eax, eax
0x1800149de  lea     r9, [rbp+440h+var_9C]
0x1800149e5  movzx   eax, [rsp+540h+var_4D4]
0x1800149ea  lea     r8, aInterfaceSU; "Interface: %s:%u"
0x1800149f1  setnz   dl
0x1800149f4  mov     dword ptr [rsp+540h+var_520], eax
0x1800149f8  test    edx, edx
0x1800149fa  mov     [rbp+440h+var_A0], edx
0x180014a00  mov     edx, 20000h
0x180014a05  cmovnz  r9, rcx
0x180014a09  lea     rcx, qword_180039310
0x180014a10  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014a17  nop     dword ptr [rax+rax+00h]
0x180014a1c  test    rbx, rbx
0x180014a1f  jnz     loc_1800148F1
0x180014a25  mov     rcx, rdi; lpCriticalSection
0x180014a28  call    cs:__imp_LeaveCriticalSection
0x180014a2f  nop     dword ptr [rax+rax+00h]
0x180014a34  mov     rcx, [rbp+440h+var_10]
0x180014a3b  xor     rcx, rsp; StackCookie
0x180014a3e  call    __security_check_cookie
0x180014a43  lea     r11, [rsp+540h+var_s0]
0x180014a4b  mov     rbx, [r11+18h]
0x180014a4f  mov     rdi, [r11+20h]
0x180014a53  mov     rsp, r11
0x180014a56  pop     rbp
0x180014a57  retn
```
