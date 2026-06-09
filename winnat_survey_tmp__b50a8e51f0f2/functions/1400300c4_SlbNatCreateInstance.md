# SlbNatCreateInstance

- ea: `0x1400300c4`
- end: `0x1400306d1`
- name: `SlbNatCreateInstance`
- size: `1549`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14002f920`
- `0x140035580`

## callees

- `0x14000c440`
- `0x14000c7a0`
- `0x14000caa0`
- `0x14000d4e4`
- `0x14000d7f8`
- `0x14000dac8`
- `0x14000e8a4`
- `0x140013b24`
- `0x140013d70`
- `0x140018f48`
- `0x1400196e0`
- `0x14002e560`
- `0x14002fda0`
- `0x14002fe34`
- `0x14002fed8`
- `0x14002ffe4`
- `0x1400300c4`
- `0x1400344f8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003066c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003066c`
- `ntoskrnl!ExAllocatePool2` at `0x14003010c`
- `ntoskrnl!ExAllocatePool2` at `0x14003010c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140030313`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140030604`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140030313`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140030604`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400302f0`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400302f0`
- `NETIO!CloseCompartment` at `0x14003065b`
- `NETIO!CloseCompartment` at `0x14003065b`

## string_xrefs

- `0x140030692`: `Create instance`

## pseudocode

```c
__int64 __fastcall SlbNatCreateInstance(NTSTRSAFE_PCWSTR pszSrc, int *a2, char a3)
{
  __int64 Pool2; // rax
  size_t v8; // rdx
  int v9; // r8d
  _QWORD *v10; // rbx
  NTSTATUS v11; // edi
  wchar_t *v12; // rbp
  __int64 AddressPool; // rax
  int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  unsigned __int8 v19; // al
  PVOID *i; // rdi
  unsigned __int8 v21; // al
  unsigned __int16 v22; // ax
  unsigned __int16 v23; // ax
  int v24; // eax
  char v25; // cl
  int v26; // r8d
  _DWORD *v27; // r9
  _QWORD *v28; // rax
  char v29; // cl
  int v30; // r8d
  _DWORD *v31; // r9
  volatile signed __int32 *v32; // rax
  __int64 v33; // rcx

  if ( !(unsigned __int8)RoReferenceEx(&dword_140026A84) )
    return 3221225860LL;
  Pool2 = ExAllocatePool2(256, 296, 1852395091);
  v10 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v11 = -1073741670;
LABEL_82:
    if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
      McTemplateK0qzqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        v8,
        v9,
        3001,
        (__int64)L"Create instance",
        0,
        v11);
    WinNatDereferenceGlobal();
    return (unsigned int)v11;
  }
  v12 = (wchar_t *)(Pool2 + 80);
  v11 = RtlStringCchCopyW((NTSTRSAFE_PWSTR)(Pool2 + 80), v8, pszSrc);
  if ( v11 < 0 )
    goto LABEL_76;
  v10[4] = v10 + 3;
  v10[3] = v10 + 3;
  v10[7] = v10 + 6;
  v10[6] = v10 + 6;
  v10[35] = _InterlockedIncrement64(&qword_140026350);
  AddressPool = WinNatLibCreateAddressPool(qword_1400263D8, v12);
  v10[2] = AddressPool;
  if ( !AddressPool )
  {
    v11 = -1073741670;
LABEL_76:
    if ( v10[2] )
      WinNatLibDeleteAddressPool(qword_1400263D8);
    v33 = v10[9];
    if ( v33 )
      CloseCompartment(v33);
    ExFreePoolWithTag(v10, 0);
    goto LABEL_81;
  }
  v14 = a2[10];
  if ( v14 == 300 )
  {
    a2[10] = dword_140026B7C;
    v14 = dword_140026B7C;
  }
  WinNatLibSetAddressPool(v10[2], a2[16], v14, a2[13], a2[14], a2[15], a2[12], *((_BYTE *)a2 + 44));
  v17 = *a2;
  if ( *a2 == 1 )
  {
    *((_DWORD *)v10 + 17) = 1;
  }
  else if ( v17 == 2 )
  {
    *((_DWORD *)v10 + 17) = 0;
  }
  else
  {
    if ( v17 != 3 )
      goto LABEL_75;
    v18 = SlbNatConvertRdIdtoCompartmentId((GUID *)(a2 + 1), v10 + 9);
    *((_DWORD *)v10 + 17) = v18;
    if ( !v18 )
    {
      v11 = -1073741264;
      goto LABEL_76;
    }
  }
  if ( *((_WORD *)a2 + 10) != 2 && *((_WORD *)a2 + 34) != 2 )
  {
    v11 = -1073741637;
    goto LABEL_76;
  }
  v19 = *((_BYTE *)a2 + 22);
  if ( v19 && v19 <= 0x20u )
    goto LABEL_89;
  LOBYTE(v16) = *((_BYTE *)a2 + 70);
  if ( !(_BYTE)v16 || (unsigned __int8)v16 > 0x20u )
  {
    v11 = -1073741820;
    goto LABEL_76;
  }
  if ( v19 )
  {
LABEL_89:
    if ( *((_BYTE *)a2 + 70) )
    {
LABEL_75:
      v11 = -1073741811;
      goto LABEL_76;
    }
  }
  *((_OWORD *)v10 + 10) = *(_OWORD *)a2;
  *((_OWORD *)v10 + 11) = *((_OWORD *)a2 + 1);
  *((_OWORD *)v10 + 12) = *((_OWORD *)a2 + 2);
  *((_OWORD *)v10 + 13) = *((_OWORD *)a2 + 3);
  *((_OWORD *)v10 + 14) = *((_OWORD *)a2 + 4);
  *(_OWORD *)((char *)v10 + 236) = *(_OWORD *)(a2 + 19);
  if ( *((_DWORD *)v10 + 64) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v16, v15);
  if ( *((_DWORD *)v10 + 65) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v16, v15);
  *((_DWORD *)v10 + 68) = 0;
  v10[33] = 0;
  if ( *((_DWORD *)v10 + 40) == 2 )
    *(__m128i *)((char *)v10 + 164) = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  if ( dword_1400264EC > 0 && *((_BYTE *)a2 + 70) || dword_1400264E8 > 0 && *((_BYTE *)a2 + 22) )
  {
    v11 = -1073741811;
LABEL_35:
    ExReleaseResourceAndLeaveCriticalRegion(&Resource);
    goto LABEL_76;
  }
  if ( SlbNatFindInstance(v12) )
  {
    v11 = -1073741635;
    goto LABEL_35;
  }
  if ( dword_1400264E8 > 0 )
  {
    for ( i = (PVOID *)qword_140026338; i != &qword_140026338; i = (PVOID *)*i )
    {
      v21 = *((_BYTE *)i + 230);
      if ( v21 >= *((_BYTE *)a2 + 70) )
        v21 = *((_BYTE *)a2 + 70);
      if ( (unsigned __int8)SlbNatIPPrefixMatch(i + 29, a2 + 18, v21) )
      {
        v11 = -1073741302;
        goto LABEL_35;
      }
    }
  }
  v10[36] = qword_140026BD8++;
  v22 = InstanceToAddressFamily(v10);
  v11 = SlbNatCheckAndRegisterChangeNotifications(v22);
  if ( v11 < 0 )
    goto LABEL_35;
  v11 = SlbNatCheckFirstInstance();
  if ( v11 >= 0 )
  {
    v23 = InstanceToAddressFamily(v10);
    v24 = SlbNatClassifyInterfaces(v23, v10, 0);
    v11 = v24;
    if ( v24 < 0 )
    {
      if ( v24 != -1073741198 || !a3 )
      {
        SlbNatCheckLastInstance();
        goto LABEL_35;
      }
      if ( dword_140026104 == 1 && (byte_140026BED & 1) != 0 )
      {
        v25 = *((_BYTE *)v10 + 230);
        v26 = (v25 == 0) + 1;
        if ( v25 )
        {
          v27 = v10 + 29;
        }
        else
        {
          v25 = *((_BYTE *)v10 + 182);
          v27 = v10 + 23;
        }
        McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          (unsigned int)WINNATM_INSTANCE_CREATION_WITH_NO_MATCHING_PREFIX,
          v26,
          (_DWORD)v12,
          (__int64)v10 + 164,
          v25,
          *v27,
          *((_DWORD *)v10 + 17),
          *((_DWORD *)v10 + 68),
          *((_DWORD *)v10 + 50),
          *((_DWORD *)v10 + 53),
          *((_DWORD *)v10 + 54),
          *((_DWORD *)v10 + 56),
          *((_DWORD *)v10 + 55),
          *((_DWORD *)v10 + 52),
          *((_BYTE *)v10 + 204),
          v26);
      }
      v11 = 0;
    }
    v28 = (_QWORD *)qword_140026340;
    if ( *(PVOID **)qword_140026340 != &qword_140026338 )
      __fastfail(3u);
    *v10 = &qword_140026338;
    v10[1] = v28;
    *v28 = v10;
    ++dword_140026348;
    qword_140026340 = (__int64)v10;
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    {
      v29 = *((_BYTE *)v10 + 230);
      v30 = (v29 == 0) + 1;
      if ( v29 )
      {
        v31 = v10 + 29;
      }
      else
      {
        v29 = *((_BYTE *)v10 + 182);
        v31 = v10 + 23;
      }
      McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_INSTANCE_CREATION,
        v30,
        (_DWORD)v12,
        (__int64)v10 + 164,
        v29,
        *v31,
        *((_DWORD *)v10 + 17),
        *((_DWORD *)v10 + 68),
        *((_DWORD *)v10 + 50),
        *((_DWORD *)v10 + 53),
        *((_DWORD *)v10 + 54),
        *((_DWORD *)v10 + 56),
        *((_DWORD *)v10 + 55),
        *((_DWORD *)v10 + 52),
        *((_BYTE *)v10 + 204),
        v30);
    }
    v10 = 0;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  v32 = &dword_1400264E8;
  if ( !*((_BYTE *)a2 + 70) )
    v32 = &dword_1400264EC;
  _InterlockedAdd(v32, 1u);
  if ( v10 )
    goto LABEL_76;
LABEL_81:
  if ( v11 < 0 )
    goto LABEL_82;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400300c4  push    rbx
0x1400300c6  push    rbp
0x1400300c7  push    rsi
0x1400300c8  push    rdi
0x1400300c9  push    r12
0x1400300cb  push    r13
0x1400300cd  push    r14
0x1400300cf  push    r15
0x1400300d1  sub     rsp, 98h
0x1400300d8  mov     rdi, rcx
0x1400300db  mov     r14b, r8b
0x1400300de  lea     rcx, dword_140026A84
0x1400300e5  mov     rsi, rdx
0x1400300e8  call    RoReferenceEx
0x1400300ed  xor     r15d, r15d
0x1400300f0  test    al, al
0x1400300f2  jnz     short loc_1400300FE
0x1400300f4  mov     eax, 0C0000184h
0x1400300f9  jmp     loc_1400306BC
0x1400300fe  mov     edx, 128h
0x140030103  mov     r8d, 6E694E53h
0x140030109  lea     ecx, [rdx-28h]
0x14003010c  call    cs:__imp_ExAllocatePool2
0x140030113  nop     dword ptr [rax+rax+00h]
0x140030118  mov     rbx, rax
0x14003011b  mov     r12d, 1
0x140030121  test    rax, rax
0x140030124  jnz     short loc_140030130
0x140030126  mov     edi, 0C000009Ah
0x14003012b  jmp     loc_14003067C
0x140030130  lea     rbp, [rax+50h]
0x140030134  mov     r8, rdi; pszSrc
0x140030137  mov     rcx, rbp; pszDest
0x14003013a  call    RtlStringCchCopyW
0x14003013f  mov     edi, eax
0x140030141  test    eax, eax
0x140030143  js      loc_14003063D
0x140030149  lea     rax, [rbx+18h]
0x14003014d  mov     r8, r12
0x140030150  mov     [rax+8], rax
0x140030154  mov     [rax], rax
0x140030157  lea     rax, [rbx+30h]
0x14003015b  mov     [rax+8], rax
0x14003015f  mov     [rax], rax
0x140030162  lock xadd cs:qword_140026350, r8
0x14003016b  add     r8, r12
0x14003016e  mov     rdx, rbp
0x140030171  mov     [rbx+118h], r8
0x140030178  mov     rcx, cs:qword_1400263D8
0x14003017f  call    WinNatLibCreateAddressPool
0x140030184  mov     [rbx+10h], rax
0x140030188  test    rax, rax
0x14003018b  jnz     short loc_140030197
0x14003018d  mov     edi, 0C000009Ah
0x140030192  jmp     loc_14003063D
0x140030197  mov     r8d, [rsi+28h]
0x14003019b  cmp     r8d, 12Ch
0x1400301a2  jnz     short loc_1400301B4
0x1400301a4  mov     eax, cs:dword_140026B7C
0x1400301aa  mov     [rsi+28h], eax
0x1400301ad  mov     r8d, cs:dword_140026B7C
0x1400301b4  mov     al, [rsi+2Ch]
0x1400301b7  mov     r9d, [rsi+34h]
0x1400301bb  mov     edx, [rsi+40h]
0x1400301be  mov     rcx, [rbx+10h]
0x1400301c2  mov     byte ptr [rsp+0D8h+var_A0], al
0x1400301c6  mov     eax, [rsi+30h]
0x1400301c9  mov     [rsp+0D8h+var_A8], eax
0x1400301cd  mov     eax, [rsi+3Ch]
0x1400301d0  mov     [rsp+0D8h+var_B0], eax
0x1400301d4  mov     eax, [rsi+38h]
0x1400301d7  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1400301db  call    WinNatLibSetAddressPool
0x1400301e0  mov     eax, [rsi]
0x1400301e2  mov     edi, 2
0x1400301e7  cmp     eax, r12d
0x1400301ea  jnz     short loc_140030206
0x1400301ec  mov     [rbx+44h], r12d
0x1400301f0  cmp     [rsi+14h], di
0x1400301f4  jz      short loc_140030237
0x1400301f6  cmp     [rsi+44h], di
0x1400301fa  jz      short loc_140030237
0x1400301fc  mov     edi, 0C00000BBh
0x140030201  jmp     loc_14003063D
0x140030206  cmp     eax, edi
0x140030208  jnz     short loc_140030210
0x14003020a  mov     [rbx+44h], r15d
0x14003020e  jmp     short loc_1400301F0
0x140030210  cmp     eax, 3
0x140030213  jnz     loc_140030638
0x140030219  lea     rdx, [rbx+48h]
0x14003021d  lea     rcx, [rsi+4]; CompartmentGuid
0x140030221  call    SlbNatConvertRdIdtoCompartmentId
0x140030226  mov     [rbx+44h], eax
0x140030229  test    eax, eax
0x14003022b  jnz     short loc_1400301F0
0x14003022d  mov     edi, 0C0000230h
0x140030232  jmp     loc_14003063D
0x140030237  mov     al, [rsi+16h]
0x14003023a  test    al, al
0x14003023c  jz      short loc_140030242
0x14003023e  cmp     al, 20h ; ' '
0x140030240  jbe     short loc_14003025A
0x140030242  mov     cl, [rsi+46h]
0x140030245  test    cl, cl
0x140030247  jz      loc_140030631
0x14003024d  cmp     cl, 20h ; ' '
0x140030250  ja      loc_140030631
0x140030256  test    al, al
0x140030258  jz      short loc_140030264
0x14003025a  cmp     [rsi+46h], r15b
0x14003025e  jnz     loc_140030638
0x140030264  movups  xmm0, xmmword ptr [rsi]
0x140030267  movups  xmmword ptr [rbx+0A0h], xmm0
0x14003026e  movups  xmm1, xmmword ptr [rsi+10h]
0x140030272  movups  xmmword ptr [rbx+0B0h], xmm1
0x140030279  movups  xmm0, xmmword ptr [rsi+20h]
0x14003027d  movups  xmmword ptr [rbx+0C0h], xmm0
0x140030284  movups  xmm1, xmmword ptr [rsi+30h]
0x140030288  movups  xmmword ptr [rbx+0D0h], xmm1
0x14003028f  movups  xmm0, xmmword ptr [rsi+40h]
0x140030293  movups  xmmword ptr [rbx+0E0h], xmm0
0x14003029a  movups  xmm1, xmmword ptr [rsi+4Ch]
0x14003029e  movups  xmmword ptr [rbx+0ECh], xmm1
0x1400302a5  cmp     [rbx+100h], r15d
0x1400302ac  jz      short loc_1400302B3
0x1400302ae  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400302b3  cmp     [rbx+104h], r15d
0x1400302ba  jz      short loc_1400302C1
0x1400302bc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400302c1  mov     [rbx+110h], r15d
0x1400302c8  mov     [rbx+108h], r15
0x1400302cf  cmp     [rbx+0A0h], edi
0x1400302d5  jnz     short loc_1400302E6
0x1400302d7  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400302df  movups  xmmword ptr [rbx+0A4h], xmm0
0x1400302e6  lea     r13, Resource
0x1400302ed  mov     rcx, r13; Resource
0x1400302f0  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400302f7  nop     dword ptr [rax+rax+00h]
0x1400302fc  cmp     cs:dword_1400264EC, r15d
0x140030303  jle     short loc_140030324
0x140030305  cmp     [rsi+46h], r15b
0x140030309  jz      short loc_140030324
0x14003030b  mov     edi, 0C000000Dh
0x140030310  mov     rcx, r13; Resource
0x140030313  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003031a  nop     dword ptr [rax+rax+00h]
0x14003031f  jmp     loc_14003063D
0x140030324  cmp     cs:dword_1400264E8, r15d
0x14003032b  jle     short loc_140030333
0x14003032d  cmp     [rsi+16h], r15b
0x140030331  jnz     short loc_14003030B
0x140030333  mov     rcx, rbp; Str2
0x140030336  call    SlbNatFindInstance
0x14003033b  test    rax, rax
0x14003033e  jz      short loc_140030347
0x140030340  mov     edi, 0C00000BDh
0x140030345  jmp     short loc_140030310
0x140030347  cmp     cs:dword_1400264E8, r15d
0x14003034e  lea     rax, qword_140026338
0x140030355  jle     short loc_1400303A1
0x140030357  mov     rdi, cs:qword_140026338
0x14003035e  cmp     rdi, rax
0x140030361  jz      short loc_1400303A1
0x140030363  movzx   ecx, byte ptr [rsi+46h]
0x140030367  lea     rdx, [rsi+48h]
0x14003036b  movzx   eax, byte ptr [rdi+0E6h]
0x140030372  cmp     al, cl
0x140030374  cmovnb  eax, ecx
0x140030377  lea     rcx, [rdi+0E8h]
0x14003037e  movzx   r8d, al
0x140030382  call    SlbNatIPPrefixMatch
0x140030387  test    al, al
0x140030389  jnz     short loc_140030397
0x14003038b  mov     rdi, [rdi]
0x14003038e  lea     rax, qword_140026338
0x140030395  jmp     short loc_14003035E
0x140030397  mov     edi, 0C000020Ah
0x14003039c  jmp     loc_140030310
0x1400303a1  mov     rax, cs:qword_140026BD8
0x1400303a8  mov     rcx, rbx
0x1400303ab  mov     [rbx+120h], rax
0x1400303b2  add     cs:qword_140026BD8, r12
0x1400303b9  call    InstanceToAddressFamily
0x1400303be  movzx   ecx, ax
0x1400303c1  call    SlbNatCheckAndRegisterChangeNotifications
0x1400303c6  mov     edi, eax
0x1400303c8  test    eax, eax
0x1400303ca  js      loc_140030310
0x1400303d0  call    SlbNatCheckFirstInstance
0x1400303d5  mov     edi, eax
0x1400303d7  test    eax, eax
0x1400303d9  js      loc_140030601
0x1400303df  mov     rcx, rbx
0x1400303e2  call    InstanceToAddressFamily
0x1400303e7  movzx   ecx, ax
0x1400303ea  xor     r8d, r8d
0x1400303ed  mov     rdx, rbx
0x1400303f0  call    SlbNatClassifyInterfaces
0x1400303f5  mov     edi, eax
0x1400303f7  test    eax, eax
0x1400303f9  jns     loc_1400304EC
0x1400303ff  cmp     eax, 0C0000272h
0x140030404  jnz     loc_140030506
0x14003040a  test    r14b, r14b
0x14003040d  jz      loc_140030506
0x140030413  cmp     cs:dword_140026104, r12d
0x14003041a  jnz     loc_1400304E9
0x140030420  test    cs:byte_140026BED, r12b
0x140030427  jz      loc_1400304E9
0x14003042d  mov     cl, [rbx+0E6h]
0x140030433  mov     r8d, r15d
0x140030436  test    cl, cl
0x140030438  setz    r8b
0x14003043c  add     r8d, r12d
0x14003043f  test    cl, cl
0x140030441  jz      short loc_14003044C
0x140030443  lea     r9, [rbx+0E8h]
0x14003044a  jmp     short loc_140030459
0x14003044c  mov     cl, [rbx+0B6h]
0x140030452  lea     r9, [rbx+0B8h]
0x140030459  movzx   eax, byte ptr [rbx+0CCh]
0x140030460  lea     rdx, [rbx+0A4h]
0x140030467  mov     [rsp+0D8h+var_58], r8d
0x14003046f  mov     [rsp+0D8h+var_60], eax
0x140030473  mov     eax, [rbx+0D0h]
0x140030479  mov     [rsp+0D8h+var_68], eax
0x14003047d  mov     eax, [rbx+0DCh]
0x140030483  mov     [rsp+0D8h+var_70], eax
0x140030487  mov     eax, [rbx+0E0h]
0x14003048d  mov     [rsp+0D8h+var_78], eax
0x140030491  mov     eax, [rbx+0D8h]
0x140030497  mov     [rsp+0D8h+var_80], eax
0x14003049b  mov     eax, [rbx+0D4h]
0x1400304a1  mov     [rsp+0D8h+var_88], eax
0x1400304a5  mov     eax, [rbx+0C8h]
0x1400304ab  mov     [rsp+0D8h+var_90], eax
0x1400304af  mov     eax, [rbx+110h]
0x1400304b5  mov     [rsp+0D8h+var_98], eax
0x1400304b9  mov     eax, [rbx+44h]
0x1400304bc  mov     [rsp+0D8h+var_A0], eax
0x1400304c0  mov     eax, [r9]
0x1400304c3  mov     r9, rbp
0x1400304c6  movzx   ecx, cl
0x1400304c9  mov     [rsp+0D8h+var_A8], eax
0x1400304cd  mov     [rsp+0D8h+var_B0], ecx
0x1400304d1  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400304d8  mov     [rsp+0D8h+var_B8], rdx
0x1400304dd  lea     rdx, WINNATM_INSTANCE_CREATION_WITH_NO_MATCHING_PREFIX
0x1400304e4  call    McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer
0x1400304e9  mov     edi, r15d
0x1400304ec  mov     rax, cs:qword_140026340
0x1400304f3  lea     rdx, qword_140026338
0x1400304fa  cmp     [rax], rdx
0x1400304fd  jz      short loc_140030510
0x1400304ff  mov     ecx, 3
0x140030504  int     29h; Win8: RtlFailFast(ecx)
0x140030506  call    SlbNatCheckLastInstance
0x14003050b  jmp     loc_140030310
0x140030510  mov     [rbx], rdx
0x140030513  mov     [rbx+8], rax
0x140030517  mov     [rax], rbx
0x14003051a  add     cs:dword_140026348, r12d
0x140030521  cmp     cs:dword_140026104, r12d
0x140030528  mov     cs:qword_140026340, rbx
0x14003052f  jnz     loc_1400305FE
0x140030535  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14003053c  jz      loc_1400305FE
0x140030542  mov     cl, [rbx+0E6h]
0x140030548  mov     r8d, r15d
0x14003054b  test    cl, cl
0x14003054d  setz    r8b
0x140030551  add     r8d, r12d
0x140030554  test    cl, cl
0x140030556  jz      short loc_140030561
0x140030558  lea     r9, [rbx+0E8h]
0x14003055f  jmp     short loc_14003056E
0x140030561  mov     cl, [rbx+0B6h]
0x140030567  lea     r9, [rbx+0B8h]
0x14003056e  movzx   eax, byte ptr [rbx+0CCh]
0x140030575  lea     rdx, [rbx+0A4h]
0x14003057c  mov     [rsp+0D8h+var_58], r8d
0x140030584  mov     [rsp+0D8h+var_60], eax
0x140030588  mov     eax, [rbx+0D0h]
0x14003058e  mov     [rsp+0D8h+var_68], eax
0x140030592  mov     eax, [rbx+0DCh]
0x140030598  mov     [rsp+0D8h+var_70], eax
0x14003059c  mov     eax, [rbx+0E0h]
0x1400305a2  mov     [rsp+0D8h+var_78], eax
0x1400305a6  mov     eax, [rbx+0D8h]
0x1400305ac  mov     [rsp+0D8h+var_80], eax
0x1400305b0  mov     eax, [rbx+0D4h]
0x1400305b6  mov     [rsp+0D8h+var_88], eax
0x1400305ba  mov     eax, [rbx+0C8h]
0x1400305c0  mov     [rsp+0D8h+var_90], eax
0x1400305c4  mov     eax, [rbx+110h]
0x1400305ca  mov     [rsp+0D8h+var_98], eax
0x1400305ce  mov     eax, [rbx+44h]
0x1400305d1  mov     [rsp+0D8h+var_A0], eax
  ... truncated ...
```
