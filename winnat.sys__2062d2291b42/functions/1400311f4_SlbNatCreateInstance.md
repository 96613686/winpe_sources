# SlbNatCreateInstance

- ea: `0x1400311f4`
- end: `0x140031801`
- name: `SlbNatCreateInstance`
- size: `1549`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc, int *, char)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x140030a50`
- `0x140036580`

## callees

- `0x14000c440`
- `0x14000c7a0`
- `0x14000caa0`
- `0x14000d4b4`
- `0x14000d7c8`
- `0x14000da98`
- `0x14000e8cc`
- `0x140014464`
- `0x1400146b0`
- `0x140019428`
- `0x140019bc0`
- `0x14002f560`
- `0x140030ed0`
- `0x140030f64`
- `0x140031008`
- `0x140031114`
- `0x1400311f4`
- `0x140035808`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003179c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003179c`
- `ntoskrnl!ExAllocatePool2` at `0x14003123c`
- `ntoskrnl!ExAllocatePool2` at `0x14003123c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140031443`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140031734`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140031443`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140031734`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140031420`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140031420`
- `NETIO!CloseCompartment` at `0x14003178b`
- `NETIO!CloseCompartment` at `0x14003178b`

## string_xrefs

- `0x1400317c2`: `Create instance`

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
  __int64 v13; // r8
  __int64 AddressPool; // rax
  int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // eax
  int v20; // eax
  unsigned __int8 v21; // al
  PVOID *i; // rdi
  unsigned __int8 v23; // al
  unsigned __int16 v24; // ax
  unsigned __int16 v25; // ax
  int v26; // eax
  char v27; // cl
  int v28; // r8d
  _DWORD *v29; // r9
  _QWORD *v30; // rax
  char v31; // cl
  int v32; // r8d
  _DWORD *v33; // r9
  volatile signed __int32 *v34; // rax

  if ( !(unsigned __int8)RoReferenceEx(&dword_140027A84) )
    return 3221225860LL;
  Pool2 = ExAllocatePool2(256, 296, 1852395091);
  v10 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v11 = -1073741670;
LABEL_82:
    if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
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
  v13 = _InterlockedIncrement64(&qword_140027350);
  v10[35] = v13;
  AddressPool = WinNatLibCreateAddressPool((__int64)qword_1400273D8, v12, v13);
  v10[2] = AddressPool;
  if ( !AddressPool )
  {
    v11 = -1073741670;
LABEL_76:
    if ( v10[2] )
      WinNatLibDeleteAddressPool(qword_1400273D8);
    if ( v10[9] )
      CloseCompartment();
    ExFreePoolWithTag(v10, 0);
    goto LABEL_81;
  }
  v15 = a2[10];
  if ( v15 == 300 )
  {
    a2[10] = dword_140027B7C;
    v15 = dword_140027B7C;
  }
  WinNatLibSetAddressPool(v10[2], a2[16], v15, a2[13], a2[14], a2[15], a2[12], *((_BYTE *)a2 + 44));
  v19 = *a2;
  if ( *a2 == 1 )
  {
    *((_DWORD *)v10 + 17) = 1;
  }
  else if ( v19 == 2 )
  {
    *((_DWORD *)v10 + 17) = 0;
  }
  else
  {
    if ( v19 != 3 )
      goto LABEL_75;
    v20 = SlbNatConvertRdIdtoCompartmentId((GUID *)(a2 + 1));
    *((_DWORD *)v10 + 17) = v20;
    if ( !v20 )
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
  v21 = *((_BYTE *)a2 + 22);
  if ( v21 && v21 <= 0x20u )
    goto LABEL_89;
  LOBYTE(v17) = *((_BYTE *)a2 + 70);
  if ( !(_BYTE)v17 || (unsigned __int8)v17 > 0x20u )
  {
    v11 = -1073741820;
    goto LABEL_76;
  }
  if ( v21 )
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
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
  if ( *((_DWORD *)v10 + 65) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
  *((_DWORD *)v10 + 68) = 0;
  v10[33] = 0;
  if ( *((_DWORD *)v10 + 40) == 2 )
    *(__m128i *)((char *)v10 + 164) = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  if ( dword_1400274EC > 0 && *((_BYTE *)a2 + 70) || dword_1400274E8 > 0 && *((_BYTE *)a2 + 22) )
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
  if ( dword_1400274E8 > 0 )
  {
    for ( i = (PVOID *)qword_140027338; i != &qword_140027338; i = (PVOID *)*i )
    {
      v23 = *((_BYTE *)i + 230);
      if ( v23 >= *((_BYTE *)a2 + 70) )
        v23 = *((_BYTE *)a2 + 70);
      if ( (unsigned __int8)SlbNatIPPrefixMatch(i + 29, a2 + 18, v23) )
      {
        v11 = -1073741302;
        goto LABEL_35;
      }
    }
  }
  v10[36] = qword_140027BD8++;
  v24 = InstanceToAddressFamily(v10);
  v11 = SlbNatCheckAndRegisterChangeNotifications(v24);
  if ( v11 < 0 )
    goto LABEL_35;
  v11 = SlbNatCheckFirstInstance();
  if ( v11 >= 0 )
  {
    v25 = InstanceToAddressFamily(v10);
    v26 = SlbNatClassifyInterfaces(v25, v10, 0);
    v11 = v26;
    if ( v26 < 0 )
    {
      if ( v26 != -1073741198 || !a3 )
      {
        SlbNatCheckLastInstance();
        goto LABEL_35;
      }
      if ( dword_140027104 == 1 && (byte_140027BED & 1) != 0 )
      {
        v27 = *((_BYTE *)v10 + 230);
        v28 = (v27 == 0) + 1;
        if ( v27 )
        {
          v29 = v10 + 29;
        }
        else
        {
          v27 = *((_BYTE *)v10 + 182);
          v29 = v10 + 23;
        }
        McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          (unsigned int)WINNATM_INSTANCE_CREATION_WITH_NO_MATCHING_PREFIX,
          v28,
          (_DWORD)v12,
          (__int64)v10 + 164,
          v27,
          *v29,
          *((_DWORD *)v10 + 17),
          *((_DWORD *)v10 + 68),
          *((_DWORD *)v10 + 50),
          *((_DWORD *)v10 + 53),
          *((_DWORD *)v10 + 54),
          *((_DWORD *)v10 + 56),
          *((_DWORD *)v10 + 55),
          *((_DWORD *)v10 + 52),
          *((_BYTE *)v10 + 204),
          v28);
      }
      v11 = 0;
    }
    v30 = (_QWORD *)qword_140027340;
    if ( *(PVOID **)qword_140027340 != &qword_140027338 )
      __fastfail(3u);
    *v10 = &qword_140027338;
    v10[1] = v30;
    *v30 = v10;
    ++dword_140027348;
    qword_140027340 = (__int64)v10;
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    {
      v31 = *((_BYTE *)v10 + 230);
      v32 = (v31 == 0) + 1;
      if ( v31 )
      {
        v33 = v10 + 29;
      }
      else
      {
        v31 = *((_BYTE *)v10 + 182);
        v33 = v10 + 23;
      }
      McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_INSTANCE_CREATION,
        v32,
        (_DWORD)v12,
        (__int64)v10 + 164,
        v31,
        *v33,
        *((_DWORD *)v10 + 17),
        *((_DWORD *)v10 + 68),
        *((_DWORD *)v10 + 50),
        *((_DWORD *)v10 + 53),
        *((_DWORD *)v10 + 54),
        *((_DWORD *)v10 + 56),
        *((_DWORD *)v10 + 55),
        *((_DWORD *)v10 + 52),
        *((_BYTE *)v10 + 204),
        v32);
    }
    v10 = 0;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  v34 = &dword_1400274E8;
  if ( !*((_BYTE *)a2 + 70) )
    v34 = &dword_1400274EC;
  _InterlockedAdd(v34, 1u);
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
0x1400311f4  push    rbx
0x1400311f6  push    rbp
0x1400311f7  push    rsi
0x1400311f8  push    rdi
0x1400311f9  push    r12
0x1400311fb  push    r13
0x1400311fd  push    r14
0x1400311ff  push    r15
0x140031201  sub     rsp, 98h
0x140031208  mov     rdi, rcx
0x14003120b  mov     r14b, r8b
0x14003120e  lea     rcx, dword_140027A84
0x140031215  mov     rsi, rdx
0x140031218  call    RoReferenceEx
0x14003121d  xor     r15d, r15d
0x140031220  test    al, al
0x140031222  jnz     short loc_14003122E
0x140031224  mov     eax, 0C0000184h
0x140031229  jmp     loc_1400317EC
0x14003122e  mov     edx, 128h
0x140031233  mov     r8d, 6E694E53h
0x140031239  lea     ecx, [rdx-28h]
0x14003123c  call    cs:__imp_ExAllocatePool2
0x140031243  nop     dword ptr [rax+rax+00h]
0x140031248  mov     rbx, rax
0x14003124b  mov     r12d, 1
0x140031251  test    rax, rax
0x140031254  jnz     short loc_140031260
0x140031256  mov     edi, 0C000009Ah
0x14003125b  jmp     loc_1400317AC
0x140031260  lea     rbp, [rax+50h]
0x140031264  mov     r8, rdi; pszSrc
0x140031267  mov     rcx, rbp; pszDest
0x14003126a  call    RtlStringCchCopyW
0x14003126f  mov     edi, eax
0x140031271  test    eax, eax
0x140031273  js      loc_14003176D
0x140031279  lea     rax, [rbx+18h]
0x14003127d  mov     r8, r12
0x140031280  mov     [rax+8], rax
0x140031284  mov     [rax], rax
0x140031287  lea     rax, [rbx+30h]
0x14003128b  mov     [rax+8], rax
0x14003128f  mov     [rax], rax
0x140031292  lock xadd cs:qword_140027350, r8
0x14003129b  add     r8, r12
0x14003129e  mov     rdx, rbp
0x1400312a1  mov     [rbx+118h], r8
0x1400312a8  mov     rcx, cs:qword_1400273D8
0x1400312af  call    WinNatLibCreateAddressPool
0x1400312b4  mov     [rbx+10h], rax
0x1400312b8  test    rax, rax
0x1400312bb  jnz     short loc_1400312C7
0x1400312bd  mov     edi, 0C000009Ah
0x1400312c2  jmp     loc_14003176D
0x1400312c7  mov     r8d, [rsi+28h]
0x1400312cb  cmp     r8d, 12Ch
0x1400312d2  jnz     short loc_1400312E4
0x1400312d4  mov     eax, cs:dword_140027B7C
0x1400312da  mov     [rsi+28h], eax
0x1400312dd  mov     r8d, cs:dword_140027B7C
0x1400312e4  mov     al, [rsi+2Ch]
0x1400312e7  mov     r9d, [rsi+34h]
0x1400312eb  mov     edx, [rsi+40h]
0x1400312ee  mov     rcx, [rbx+10h]
0x1400312f2  mov     byte ptr [rsp+0D8h+var_A0], al
0x1400312f6  mov     eax, [rsi+30h]
0x1400312f9  mov     [rsp+0D8h+var_A8], eax
0x1400312fd  mov     eax, [rsi+3Ch]
0x140031300  mov     [rsp+0D8h+var_B0], eax
0x140031304  mov     eax, [rsi+38h]
0x140031307  mov     dword ptr [rsp+0D8h+var_B8], eax
0x14003130b  call    WinNatLibSetAddressPool
0x140031310  mov     eax, [rsi]
0x140031312  mov     edi, 2
0x140031317  cmp     eax, r12d
0x14003131a  jnz     short loc_140031336
0x14003131c  mov     [rbx+44h], r12d
0x140031320  cmp     [rsi+14h], di
0x140031324  jz      short loc_140031367
0x140031326  cmp     [rsi+44h], di
0x14003132a  jz      short loc_140031367
0x14003132c  mov     edi, 0C00000BBh
0x140031331  jmp     loc_14003176D
0x140031336  cmp     eax, edi
0x140031338  jnz     short loc_140031340
0x14003133a  mov     [rbx+44h], r15d
0x14003133e  jmp     short loc_140031320
0x140031340  cmp     eax, 3
0x140031343  jnz     loc_140031768
0x140031349  lea     rdx, [rbx+48h]
0x14003134d  lea     rcx, [rsi+4]; CompartmentGuid
0x140031351  call    SlbNatConvertRdIdtoCompartmentId
0x140031356  mov     [rbx+44h], eax
0x140031359  test    eax, eax
0x14003135b  jnz     short loc_140031320
0x14003135d  mov     edi, 0C0000230h
0x140031362  jmp     loc_14003176D
0x140031367  mov     al, [rsi+16h]
0x14003136a  test    al, al
0x14003136c  jz      short loc_140031372
0x14003136e  cmp     al, 20h ; ' '
0x140031370  jbe     short loc_14003138A
0x140031372  mov     cl, [rsi+46h]
0x140031375  test    cl, cl
0x140031377  jz      loc_140031761
0x14003137d  cmp     cl, 20h ; ' '
0x140031380  ja      loc_140031761
0x140031386  test    al, al
0x140031388  jz      short loc_140031394
0x14003138a  cmp     [rsi+46h], r15b
0x14003138e  jnz     loc_140031768
0x140031394  movups  xmm0, xmmword ptr [rsi]
0x140031397  movups  xmmword ptr [rbx+0A0h], xmm0
0x14003139e  movups  xmm1, xmmword ptr [rsi+10h]
0x1400313a2  movups  xmmword ptr [rbx+0B0h], xmm1
0x1400313a9  movups  xmm0, xmmword ptr [rsi+20h]
0x1400313ad  movups  xmmword ptr [rbx+0C0h], xmm0
0x1400313b4  movups  xmm1, xmmword ptr [rsi+30h]
0x1400313b8  movups  xmmword ptr [rbx+0D0h], xmm1
0x1400313bf  movups  xmm0, xmmword ptr [rsi+40h]
0x1400313c3  movups  xmmword ptr [rbx+0E0h], xmm0
0x1400313ca  movups  xmm1, xmmword ptr [rsi+4Ch]
0x1400313ce  movups  xmmword ptr [rbx+0ECh], xmm1
0x1400313d5  cmp     [rbx+100h], r15d
0x1400313dc  jz      short loc_1400313E3
0x1400313de  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400313e3  cmp     [rbx+104h], r15d
0x1400313ea  jz      short loc_1400313F1
0x1400313ec  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400313f1  mov     [rbx+110h], r15d
0x1400313f8  mov     [rbx+108h], r15
0x1400313ff  cmp     [rbx+0A0h], edi
0x140031405  jnz     short loc_140031416
0x140031407  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14003140f  movups  xmmword ptr [rbx+0A4h], xmm0
0x140031416  lea     r13, Resource
0x14003141d  mov     rcx, r13; Resource
0x140031420  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140031427  nop     dword ptr [rax+rax+00h]
0x14003142c  cmp     cs:dword_1400274EC, r15d
0x140031433  jle     short loc_140031454
0x140031435  cmp     [rsi+46h], r15b
0x140031439  jz      short loc_140031454
0x14003143b  mov     edi, 0C000000Dh
0x140031440  mov     rcx, r13; Resource
0x140031443  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003144a  nop     dword ptr [rax+rax+00h]
0x14003144f  jmp     loc_14003176D
0x140031454  cmp     cs:dword_1400274E8, r15d
0x14003145b  jle     short loc_140031463
0x14003145d  cmp     [rsi+16h], r15b
0x140031461  jnz     short loc_14003143B
0x140031463  mov     rcx, rbp; Str2
0x140031466  call    SlbNatFindInstance
0x14003146b  test    rax, rax
0x14003146e  jz      short loc_140031477
0x140031470  mov     edi, 0C00000BDh
0x140031475  jmp     short loc_140031440
0x140031477  cmp     cs:dword_1400274E8, r15d
0x14003147e  lea     rax, qword_140027338
0x140031485  jle     short loc_1400314D1
0x140031487  mov     rdi, cs:qword_140027338
0x14003148e  cmp     rdi, rax
0x140031491  jz      short loc_1400314D1
0x140031493  movzx   ecx, byte ptr [rsi+46h]
0x140031497  lea     rdx, [rsi+48h]
0x14003149b  movzx   eax, byte ptr [rdi+0E6h]
0x1400314a2  cmp     al, cl
0x1400314a4  cmovnb  eax, ecx
0x1400314a7  lea     rcx, [rdi+0E8h]
0x1400314ae  movzx   r8d, al
0x1400314b2  call    SlbNatIPPrefixMatch
0x1400314b7  test    al, al
0x1400314b9  jnz     short loc_1400314C7
0x1400314bb  mov     rdi, [rdi]
0x1400314be  lea     rax, qword_140027338
0x1400314c5  jmp     short loc_14003148E
0x1400314c7  mov     edi, 0C000020Ah
0x1400314cc  jmp     loc_140031440
0x1400314d1  mov     rax, cs:qword_140027BD8
0x1400314d8  mov     rcx, rbx
0x1400314db  mov     [rbx+120h], rax
0x1400314e2  add     cs:qword_140027BD8, r12
0x1400314e9  call    InstanceToAddressFamily
0x1400314ee  movzx   ecx, ax
0x1400314f1  call    SlbNatCheckAndRegisterChangeNotifications
0x1400314f6  mov     edi, eax
0x1400314f8  test    eax, eax
0x1400314fa  js      loc_140031440
0x140031500  call    SlbNatCheckFirstInstance
0x140031505  mov     edi, eax
0x140031507  test    eax, eax
0x140031509  js      loc_140031731
0x14003150f  mov     rcx, rbx
0x140031512  call    InstanceToAddressFamily
0x140031517  movzx   ecx, ax
0x14003151a  xor     r8d, r8d
0x14003151d  mov     rdx, rbx
0x140031520  call    SlbNatClassifyInterfaces
0x140031525  mov     edi, eax
0x140031527  test    eax, eax
0x140031529  jns     loc_14003161C
0x14003152f  cmp     eax, 0C0000272h
0x140031534  jnz     loc_140031636
0x14003153a  test    r14b, r14b
0x14003153d  jz      loc_140031636
0x140031543  cmp     cs:dword_140027104, r12d
0x14003154a  jnz     loc_140031619
0x140031550  test    cs:byte_140027BED, r12b
0x140031557  jz      loc_140031619
0x14003155d  mov     cl, [rbx+0E6h]
0x140031563  mov     r8d, r15d
0x140031566  test    cl, cl
0x140031568  setz    r8b
0x14003156c  add     r8d, r12d
0x14003156f  test    cl, cl
0x140031571  jz      short loc_14003157C
0x140031573  lea     r9, [rbx+0E8h]
0x14003157a  jmp     short loc_140031589
0x14003157c  mov     cl, [rbx+0B6h]
0x140031582  lea     r9, [rbx+0B8h]
0x140031589  movzx   eax, byte ptr [rbx+0CCh]
0x140031590  lea     rdx, [rbx+0A4h]
0x140031597  mov     [rsp+0D8h+var_58], r8d
0x14003159f  mov     [rsp+0D8h+var_60], eax
0x1400315a3  mov     eax, [rbx+0D0h]
0x1400315a9  mov     [rsp+0D8h+var_68], eax
0x1400315ad  mov     eax, [rbx+0DCh]
0x1400315b3  mov     [rsp+0D8h+var_70], eax
0x1400315b7  mov     eax, [rbx+0E0h]
0x1400315bd  mov     [rsp+0D8h+var_78], eax
0x1400315c1  mov     eax, [rbx+0D8h]
0x1400315c7  mov     [rsp+0D8h+var_80], eax
0x1400315cb  mov     eax, [rbx+0D4h]
0x1400315d1  mov     [rsp+0D8h+var_88], eax
0x1400315d5  mov     eax, [rbx+0C8h]
0x1400315db  mov     [rsp+0D8h+var_90], eax
0x1400315df  mov     eax, [rbx+110h]
0x1400315e5  mov     [rsp+0D8h+var_98], eax
0x1400315e9  mov     eax, [rbx+44h]
0x1400315ec  mov     [rsp+0D8h+var_A0], eax
0x1400315f0  mov     eax, [r9]
0x1400315f3  mov     r9, rbp
0x1400315f6  movzx   ecx, cl
0x1400315f9  mov     [rsp+0D8h+var_A8], eax
0x1400315fd  mov     [rsp+0D8h+var_B0], ecx
0x140031601  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140031608  mov     [rsp+0D8h+var_B8], rdx
0x14003160d  lea     rdx, WINNATM_INSTANCE_CREATION_WITH_NO_MATCHING_PREFIX
0x140031614  call    McTemplateK0zjqqqqqqqqqqtq_EtwWriteTransfer
0x140031619  mov     edi, r15d
0x14003161c  mov     rax, cs:qword_140027340
0x140031623  lea     rdx, qword_140027338
0x14003162a  cmp     [rax], rdx
0x14003162d  jz      short loc_140031640
0x14003162f  mov     ecx, 3
0x140031634  int     29h; Win8: RtlFailFast(ecx)
0x140031636  call    SlbNatCheckLastInstance
0x14003163b  jmp     loc_140031440
0x140031640  mov     [rbx], rdx
0x140031643  mov     [rbx+8], rax
0x140031647  mov     [rax], rbx
0x14003164a  add     cs:dword_140027348, r12d
0x140031651  cmp     cs:dword_140027104, r12d
0x140031658  mov     cs:qword_140027340, rbx
0x14003165f  jnz     loc_14003172E
0x140031665  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14003166c  jz      loc_14003172E
0x140031672  mov     cl, [rbx+0E6h]
0x140031678  mov     r8d, r15d
0x14003167b  test    cl, cl
0x14003167d  setz    r8b
0x140031681  add     r8d, r12d
0x140031684  test    cl, cl
0x140031686  jz      short loc_140031691
0x140031688  lea     r9, [rbx+0E8h]
0x14003168f  jmp     short loc_14003169E
0x140031691  mov     cl, [rbx+0B6h]
0x140031697  lea     r9, [rbx+0B8h]
0x14003169e  movzx   eax, byte ptr [rbx+0CCh]
0x1400316a5  lea     rdx, [rbx+0A4h]
0x1400316ac  mov     [rsp+0D8h+var_58], r8d
0x1400316b4  mov     [rsp+0D8h+var_60], eax
0x1400316b8  mov     eax, [rbx+0D0h]
0x1400316be  mov     [rsp+0D8h+var_68], eax
0x1400316c2  mov     eax, [rbx+0DCh]
0x1400316c8  mov     [rsp+0D8h+var_70], eax
0x1400316cc  mov     eax, [rbx+0E0h]
0x1400316d2  mov     [rsp+0D8h+var_78], eax
0x1400316d6  mov     eax, [rbx+0D8h]
0x1400316dc  mov     [rsp+0D8h+var_80], eax
0x1400316e0  mov     eax, [rbx+0D4h]
0x1400316e6  mov     [rsp+0D8h+var_88], eax
0x1400316ea  mov     eax, [rbx+0C8h]
0x1400316f0  mov     [rsp+0D8h+var_90], eax
0x1400316f4  mov     eax, [rbx+110h]
0x1400316fa  mov     [rsp+0D8h+var_98], eax
0x1400316fe  mov     eax, [rbx+44h]
0x140031701  mov     [rsp+0D8h+var_A0], eax
  ... truncated ...
```
