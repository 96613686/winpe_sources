# TdxCreateAndRegisterDeviceObject

- ea: `0x14000db08`
- end: `0x14000e1a4`
- name: `TdxCreateAndRegisterDeviceObject`
- size: `1692`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x14000cfc0`
- `0x14000eba0`

## callees

- `0x14000db08`
- `0x14000e1b0`
- `0x14000e4ec`
- `0x14000f364`
- `0x140010c2c`
- `0x140012b5c`
- `0x1400151d0`
- `0x140015284`
- `0x1400152e0`
- `0x1400184b0`
- `0x140018900`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000dcd4`
- `ntoskrnl!ExAllocatePool2` at `0x14000dcd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000def0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000def0`
- `NETIO!NsiGetParameter` at `0x14000dbd3`
- `NETIO!NsiGetParameter` at `0x14000dc7c`
- `NETIO!NsiGetParameter` at `0x14000dbd3`
- `NETIO!NsiGetParameter` at `0x14000dc7c`
- `NETIO!NsiGetAllParameters` at `0x14000dea3`
- `NETIO!NsiGetAllParameters` at `0x14000dea3`
- `TDI!TdiRegisterDeviceObject` at `0x14000e114`
- `TDI!TdiRegisterDeviceObject` at `0x14000e114`

## pseudocode

```c
__int64 __fastcall TdxCreateAndRegisterDeviceObject(
        __int64 *a1,
        int a2,
        struct _DEVICE_OBJECT *a3,
        struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **a4)
{
  unsigned int Parameter; // eax
  PDEVICE_OBJECT v8; // r8
  __int64 v9; // rdx
  __int64 result; // rax
  __int64 Pool2; // rax
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C *v12; // r12
  signed __int32 v13; // eax
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C *v14; // r13
  __int64 v15; // rcx
  __int64 v16; // rax
  char v17; // di
  bool v18; // zf
  const NPI_MODULEID *v19; // rdx
  int AllParameters; // eax
  unsigned int v21; // ebx
  int v22; // ecx
  int v23; // edx
  int v24; // ecx
  NTSTATUS v25; // eax
  __int64 v26; // r8
  PDEVICE_OBJECT v27; // rdx
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v28; // rax
  __int64 v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-C8h]
  __int64 v33; // [rsp+40h] [rbp-C0h]
  int v34; // [rsp+84h] [rbp-7Ch] BYREF
  PDEVICE_OBJECT v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v38; // [rsp+A0h] [rbp-60h]
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **v39; // [rsp+A8h] [rbp-58h]
  _QWORD v40[12]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v41; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v42[240]; // [rsp+120h] [rbp+20h] BYREF

  v35 = a3;
  v36 = a2;
  v38 = a1;
  v39 = a4;
  v34 = 0;
  v37 = 0;
  v41 = 0;
  memset(v42, 0, sizeof(v42));
  memset(v40, 0, 0x58u);
  if ( TdxFindDeviceObject((__int64 **)&WPP_MAIN_CB.DeviceQueue.32, *a1, a2) )
    return 3221225473LL;
  Parameter = NsiGetParameter(3, &NPI_MS_NDIS_MODULEID, 0, a1, 8, 2, &v41, 16, 536);
  if ( Parameter )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      return 3221225473LL;
    }
    v9 = 21;
LABEL_7:
    WPP_SF_d(v8->AttachedDevice, v9, v8, Parameter);
    return 3221225473LL;
  }
  Parameter = NsiGetParameter(3, &NPI_MS_NDIS_MODULEID, 0, a1, 8, 1, &v34, 4, 8);
  if ( Parameter )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      return 3221225473LL;
    }
    v9 = 22;
    goto LABEL_7;
  }
  Pool2 = ExAllocatePool2(64, 312, 1870160980);
  v12 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids);
    }
    return 3221225495LL;
  }
  *(_DWORD *)(Pool2 + 16) = 1;
  *(_DWORD *)(Pool2 + 20) = a2;
  *(_QWORD *)(Pool2 + 24) = *a1;
  v13 = _InterlockedIncrement(&TdxTdiInstanceIdBase);
  *(_DWORD *)&v12[4] = v13;
  if ( v13 == -1 )
    *(_DWORD *)&v12[4] = _InterlockedIncrement(&TdxTdiInstanceIdBase);
  v14 = v12 + 7;
  v12[6] = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)&v12[7];
  *((_WORD *)&v12[5] + 1) = 112;
  *((_DWORD *)&v12[4] + 1) = a3->ReferenceCount;
  if ( a2 )
  {
    v15 = 86;
    *(_OWORD *)v14 = *(_OWORD *)L"\\DEVICE\\TCPIP6_";
    *(_OWORD *)((char *)&v12[8] + 6) = *(_OWORD *)L"\\TCPIP6_";
  }
  else
  {
    v15 = 84;
    *(_OWORD *)v14 = *(_OWORD *)L"\\DEVICE\\TCPIP_";
    *(_OWORD *)((char *)&v12[8] + 4) = *(_OWORD *)L"E\\TCPIP_";
  }
  LODWORD(v33) = BYTE10(v41);
  LODWORD(v32) = BYTE9(v41);
  LODWORD(v31) = BYTE8(v41);
  LODWORD(v30) = WORD3(v41);
  LODWORD(v29) = WORD2(v41);
  StringCbPrintfW(
    (STRSAFE_LPWSTR)((char *)v12 + v15),
    0x70u,
    L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    (unsigned int)v41,
    v29,
    v30,
    v31,
    v32,
    v33,
    BYTE11(v41),
    BYTE12(v41),
    BYTE13(v41),
    BYTE14(v41),
    HIBYTE(v41));
  v16 = -1;
  v17 = 0;
  do
    ++v16;
  while ( *((_WORD *)v14 + v16) );
  v18 = v36 == 0;
  v19 = &NPI_MS_IPV4_MODULEID;
  *(_WORD *)&v12[5] = 2 * v16;
  v37 = *v38;
  if ( !v18 )
    v19 = &NPI_MS_IPV6_MODULEID;
  AllParameters = NsiGetAllParameters(3, v19, 7, &v37, 8, v42, 240, v40, 88, 0, 0);
  v21 = AllParameters;
  if ( AllParameters < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_GLOBAL_Control, (unsigned int)AllParameters);
    }
LABEL_34:
    ExFreePoolWithTag(v12, 0x6F786454u);
    return v21;
  }
  v22 = (int)v12[38];
  *(_DWORD *)&v12[36] = v34;
  v12[37] = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)v40[3];
  if ( v35->ReferenceCount == 6 )
  {
    if ( v34 == 2 )
    {
      v24 = v22 | 4;
      *(_DWORD *)&v12[38] = v24;
      *(_DWORD *)&v12[38] = v24 ^ ((unsigned __int8)v24 ^ v42[10]) & 1;
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
      {
        v23 = 26;
        goto LABEL_45;
      }
    }
    else
    {
      *(_DWORD *)&v12[38] = v22 ^ ((unsigned __int8)v22 ^ v42[10]) & 1;
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
      {
        WPP_SF_qLDDDDDDDDDD(
          v35->AttachedDevice,
          27,
          BYTE13(v41),
          (_DWORD)v12,
          v41,
          SBYTE4(v41),
          SBYTE6(v41),
          SBYTE8(v41),
          SBYTE9(v41),
          SBYTE10(v41),
          SBYTE11(v41),
          SBYTE12(v41),
          SBYTE13(v41),
          SBYTE14(v41),
          SHIBYTE(v41));
      }
      v17 = 1;
      TdxIncrementNotReadyInterfaceCount(994);
    }
  }
  else
  {
    *(_DWORD *)&v12[38] = v22 | 4;
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      v23 = 25;
LABEL_45:
      WPP_SF_qLDDDDDDDDDD(
        v35->AttachedDevice,
        v23,
        BYTE13(v41),
        (_DWORD)v12,
        v41,
        SBYTE4(v41),
        SBYTE6(v41),
        SBYTE8(v41),
        SBYTE9(v41),
        SBYTE10(v41),
        SBYTE11(v41),
        SBYTE12(v41),
        SBYTE13(v41),
        SBYTE14(v41),
        SHIBYTE(v41));
      v17 = 0;
    }
  }
  v25 = TdiRegisterDeviceObject((PUNICODE_STRING)&v12[5], (HANDLE *)&v12[35]);
  v21 = v25;
  if ( v25 < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v26, v12, v25);
    }
    if ( v17 )
      TdxDecrementNotReadyInterfaceCount(0x3F2u, (__int64)v27, v26);
    goto LABEL_34;
  }
  *v39 = v12;
  v28 = WPP_MAIN_CB.DeviceQueue.1;
  if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 8LL) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
    __fastfail(3u);
  *v12 = WPP_MAIN_CB.DeviceQueue.1;
  v12[1] = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)&WPP_MAIN_CB.DeviceQueue.1;
  *(_QWORD *)(*(_QWORD *)&v28 + 8LL) = v12;
  result = 0;
  WPP_MAIN_CB.DeviceQueue.1 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)v12;
  return result;
}

```

## disassembly

```asm
0x14000db08  mov     [rsp-8+arg_10], rbx
0x14000db0d  push    rbp
0x14000db0e  push    rsi
0x14000db0f  push    rdi
0x14000db10  push    r12
0x14000db12  push    r13
0x14000db14  push    r14
0x14000db16  push    r15
0x14000db18  lea     rbp, [rsp-120h]
0x14000db20  sub     rsp, 220h
0x14000db27  mov     rax, cs:__security_cookie
0x14000db2e  xor     rax, rsp
0x14000db31  mov     [rbp+150h+var_40], rax
0x14000db38  mov     rsi, r8
0x14000db3b  mov     [rbp+150h+var_1C8], r8
0x14000db3f  mov     edi, edx
0x14000db41  mov     [rbp+150h+var_1C0], edx
0x14000db44  mov     rbx, rcx
0x14000db47  mov     [rbp+150h+var_1B0], rcx
0x14000db4b  xorps   xmm0, xmm0
0x14000db4e  mov     [rbp+150h+var_1A8], r9
0x14000db52  xor     r14d, r14d
0x14000db55  lea     rcx, [rbp+150h+var_130]; void *
0x14000db59  xor     edx, edx; Val
0x14000db5b  mov     [rbp+150h+var_1CC], r14d
0x14000db5f  mov     r8d, 0F0h; Size
0x14000db65  mov     [rbp+150h+var_1B8], r14
0x14000db69  movups  [rbp+150h+var_140], xmm0
0x14000db6d  call    memset
0x14000db72  xor     edx, edx; Val
0x14000db74  lea     r8d, [r14+58h]; Size
0x14000db78  lea     rcx, [rbp+150h+var_1A0]; void *
0x14000db7c  call    memset
0x14000db81  mov     rdx, [rbx]
0x14000db84  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h
0x14000db8b  mov     r8d, edi
0x14000db8e  call    TdxFindDeviceObject
0x14000db93  test    rax, rax
0x14000db96  jnz     short loc_14000DC15
0x14000db98  mov     dword ptr [rsp+250h+var_210], 218h
0x14000dba0  lea     rax, [rbp+150h+var_140]
0x14000dba4  mov     dword ptr [rsp+250h+var_218], 10h
0x14000dbac  lea     r12d, [r14+8]
0x14000dbb0  mov     [rsp+250h+var_220], rax
0x14000dbb5  lea     rdx, NPI_MS_NDIS_MODULEID
0x14000dbbc  mov     dword ptr [rsp+250h+var_228], 2
0x14000dbc4  lea     ecx, [r14+3]
0x14000dbc8  mov     r9, rbx
0x14000dbcb  mov     dword ptr [rsp+250h+var_230], r12d
0x14000dbd0  xor     r8d, r8d
0x14000dbd3  call    cs:__imp_NsiGetParameter
0x14000dbda  nop     dword ptr [rax+rax+00h]
0x14000dbdf  test    eax, eax
0x14000dbe1  jz      short loc_14000DC45
0x14000dbe3  mov     r8, cs:WPP_GLOBAL_Control
0x14000dbea  lea     r15, WPP_GLOBAL_Control
0x14000dbf1  cmp     r8, r15
0x14000dbf4  jz      short loc_14000DC15
0x14000dbf6  cmp     byte ptr [r8+29h], 3
0x14000dbfb  jb      short loc_14000DC15
0x14000dbfd  bt      dword ptr [r8+2Ch], 9
0x14000dc03  jnb     short loc_14000DC15
0x14000dc05  lea     edx, [r14+15h]
0x14000dc09  mov     rcx, [r8+18h]
0x14000dc0d  mov     r9d, eax
0x14000dc10  call    WPP_SF_d
0x14000dc15  mov     eax, 0C0000001h
0x14000dc1a  mov     rcx, [rbp+150h+var_40]
0x14000dc21  xor     rcx, rsp; StackCookie
0x14000dc24  call    __security_check_cookie
0x14000dc29  mov     rbx, [rsp+250h+arg_10]
0x14000dc31  add     rsp, 220h
0x14000dc38  pop     r15
0x14000dc3a  pop     r14
0x14000dc3c  pop     r13
0x14000dc3e  pop     r12
0x14000dc40  pop     rdi
0x14000dc41  pop     rsi
0x14000dc42  pop     rbp
0x14000dc43  retn
0x14000dc45  mov     dword ptr [rsp+250h+var_210], r12d
0x14000dc4a  lea     rax, [rbp+150h+var_1CC]
0x14000dc4e  mov     dword ptr [rsp+250h+var_218], 4
0x14000dc56  lea     rdx, NPI_MS_NDIS_MODULEID
0x14000dc5d  mov     [rsp+250h+var_220], rax
0x14000dc62  mov     r15d, 1
0x14000dc68  mov     dword ptr [rsp+250h+var_228], r15d
0x14000dc6d  mov     r9, rbx
0x14000dc70  xor     r8d, r8d
0x14000dc73  mov     dword ptr [rsp+250h+var_230], r12d
0x14000dc78  lea     ecx, [r15+2]
0x14000dc7c  call    cs:__imp_NsiGetParameter
0x14000dc83  nop     dword ptr [rax+rax+00h]
0x14000dc88  test    eax, eax
0x14000dc8a  jz      short loc_14000DCC4
0x14000dc8c  mov     r8, cs:WPP_GLOBAL_Control
0x14000dc93  lea     r15, WPP_GLOBAL_Control
0x14000dc9a  cmp     r8, r15
0x14000dc9d  jz      loc_14000DC15
0x14000dca3  cmp     byte ptr [r8+29h], 3
0x14000dca8  jb      loc_14000DC15
0x14000dcae  bt      dword ptr [r8+2Ch], 9
0x14000dcb4  jnb     loc_14000DC15
0x14000dcba  mov     edx, 16h
0x14000dcbf  jmp     loc_14000DC09
0x14000dcc4  mov     edx, 138h
0x14000dcc9  mov     ecx, 40h ; '@'
0x14000dcce  mov     r8d, 6F786454h
0x14000dcd4  call    cs:__imp_ExAllocatePool2
0x14000dcdb  nop     dword ptr [rax+rax+00h]
0x14000dce0  mov     r12, rax
0x14000dce3  test    rax, rax
0x14000dce6  jnz     short loc_14000DD25
0x14000dce8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dcef  lea     r15, WPP_GLOBAL_Control
0x14000dcf6  cmp     rcx, r15
0x14000dcf9  jz      short loc_14000DD1B
0x14000dcfb  cmp     byte ptr [rcx+29h], 3
0x14000dcff  jb      short loc_14000DD1B
0x14000dd01  bt      dword ptr [rcx+2Ch], 9
0x14000dd06  jnb     short loc_14000DD1B
0x14000dd08  mov     rcx, [rcx+18h]
0x14000dd0c  lea     edx, [rax+17h]
0x14000dd0f  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000dd16  call    WPP_SF_
0x14000dd1b  mov     eax, 0C0000017h
0x14000dd20  jmp     loc_14000DC1A
0x14000dd25  mov     [rax+10h], r15d
0x14000dd29  mov     [rax+14h], edi
0x14000dd2c  mov     rax, [rbx]
0x14000dd2f  mov     [r12+18h], rax
0x14000dd34  mov     eax, r15d
0x14000dd37  lock xadd cs:TdxTdiInstanceIdBase, eax
0x14000dd3f  add     eax, r15d
0x14000dd42  mov     [r12+20h], eax
0x14000dd47  cmp     eax, 0FFFFFFFFh
0x14000dd4a  jnz     short loc_14000DD5F
0x14000dd4c  mov     eax, r15d
0x14000dd4f  lock xadd cs:TdxTdiInstanceIdBase, eax
0x14000dd57  add     eax, r15d
0x14000dd5a  mov     [r12+20h], eax
0x14000dd5f  lea     r13, [r12+38h]
0x14000dd64  mov     edx, 70h ; 'p'; cbDest
0x14000dd69  mov     [r12+30h], r13
0x14000dd6e  mov     [r12+2Ah], dx
0x14000dd74  mov     eax, [rsi+4]
0x14000dd77  mov     [r12+24h], eax
0x14000dd7c  test    edi, edi
0x14000dd7e  jnz     short loc_14000DD9D
0x14000dd80  movups  xmm0, xmmword ptr cs:aDeviceTcpip; "\\DEVICE\\TCPIP_"
0x14000dd87  lea     ecx, [rdx-1Ch]
0x14000dd8a  movups  xmmword ptr [r13+0], xmm0
0x14000dd8f  movups  xmm1, xmmword ptr cs:aDeviceTcpip+0Ch; "E\\TCPIP_"
0x14000dd96  movups  xmmword ptr [r13+0Ch], xmm1
0x14000dd9b  jmp     short loc_14000DDBA
0x14000dd9d  movups  xmm0, xmmword ptr cs:aDeviceTcpip6; "\\DEVICE\\TCPIP6_"
0x14000dda4  mov     ecx, 56h ; 'V'
0x14000dda9  movups  xmmword ptr [r13+0], xmm0
0x14000ddae  movups  xmm1, xmmword ptr cs:aDeviceTcpip6+0Eh; "\\TCPIP6_"
0x14000ddb5  movups  xmmword ptr [r13+0Eh], xmm1
0x14000ddba  movzx   r8d, byte ptr [rbp+150h+var_140+0Eh]
0x14000ddbf  add     rcx, r12; pszDest
0x14000ddc2  movzx   r9d, byte ptr [rbp+150h+var_140+0Dh]
0x14000ddc7  movzx   eax, byte ptr [rbp+150h+var_140+0Fh]
0x14000ddcb  movzx   r10d, byte ptr [rbp+150h+var_140+0Ch]
0x14000ddd0  movzx   r11d, byte ptr [rbp+150h+var_140+0Bh]
0x14000ddd5  movzx   ebx, byte ptr [rbp+150h+var_140+0Ah]
0x14000ddd9  movzx   edi, byte ptr [rbp+150h+var_140+9]
0x14000dddd  movzx   esi, byte ptr [rbp+150h+var_140+8]
0x14000dde1  movzx   r14d, word ptr [rbp+150h+var_140+6]
0x14000dde6  movzx   r15d, word ptr [rbp+150h+var_140+4]
0x14000ddeb  mov     [rsp+250h+var_1E8], eax
0x14000ddef  mov     [rsp+250h+var_1F0], r8d
0x14000ddf4  lea     r8, TdxGuidFormat; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x14000ddfb  mov     [rsp+250h+var_1F8], r9d
0x14000de00  mov     r9d, dword ptr [rbp+150h+var_140]
0x14000de04  mov     [rsp+250h+var_200], r10d
0x14000de09  mov     dword ptr [rsp+250h+var_208], r11d
0x14000de0e  mov     dword ptr [rsp+250h+var_210], ebx
0x14000de12  mov     dword ptr [rsp+250h+var_218], edi
0x14000de16  mov     dword ptr [rsp+250h+var_220], esi
0x14000de1a  mov     dword ptr [rsp+250h+var_228], r14d
0x14000de1f  mov     dword ptr [rsp+250h+var_230], r15d
0x14000de24  call    StringCbPrintfW
0x14000de29  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000de2d  xor     edi, edi
0x14000de2f  inc     rax
0x14000de32  cmp     [r13+rax*2+0], di
0x14000de38  jnz     short loc_14000DE2F
0x14000de3a  add     ax, ax
0x14000de3d  mov     [rsp+250h+var_200], edi
0x14000de41  cmp     [rbp+150h+var_1C0], edi
0x14000de44  lea     rdx, NPI_MS_IPV4_MODULEID
0x14000de4b  mov     [r12+28h], ax
0x14000de51  lea     r9, [rbp+150h+var_1B8]
0x14000de55  mov     rax, [rbp+150h+var_1B0]
0x14000de59  mov     ecx, 3
0x14000de5e  mov     [rsp+250h+var_208], rdi
0x14000de63  mov     dword ptr [rsp+250h+var_210], 58h ; 'X'
0x14000de6b  mov     rax, [rax]
0x14000de6e  lea     r8d, [rcx+4]
0x14000de72  mov     [rbp+150h+var_1B8], rax
0x14000de76  lea     rax, NPI_MS_IPV6_MODULEID
0x14000de7d  cmovnz  rdx, rax
0x14000de81  lea     rax, [rbp+150h+var_1A0]
0x14000de85  mov     [rsp+250h+var_218], rax
0x14000de8a  lea     rax, [rbp+150h+var_130]
0x14000de8e  mov     dword ptr [rsp+250h+var_220], 0F0h
0x14000de96  mov     [rsp+250h+var_228], rax
0x14000de9b  mov     dword ptr [rsp+250h+var_230], 8
0x14000dea3  call    cs:__imp_NsiGetAllParameters
0x14000deaa  nop     dword ptr [rax+rax+00h]
0x14000deaf  mov     ebx, eax
0x14000deb1  test    eax, eax
0x14000deb3  jns     short loc_14000DF03
0x14000deb5  mov     r8, cs:WPP_GLOBAL_Control
0x14000debc  lea     r15, WPP_GLOBAL_Control
0x14000dec3  cmp     r8, r15
0x14000dec6  jz      short loc_14000DEE8
0x14000dec8  cmp     byte ptr [r8+29h], 3
0x14000decd  jb      short loc_14000DEE8
0x14000decf  bt      dword ptr [r8+2Ch], 9
0x14000ded5  jnb     short loc_14000DEE8
0x14000ded7  mov     rcx, [r8+18h]
0x14000dedb  mov     edx, 18h
0x14000dee0  mov     r9d, eax
0x14000dee3  call    WPP_SF_d
0x14000dee8  mov     edx, 6F786454h; Tag
0x14000deed  mov     rcx, r12; P
0x14000def0  call    cs:__imp_ExFreePoolWithTag
0x14000def7  nop     dword ptr [rax+rax+00h]
0x14000defc  mov     eax, ebx
0x14000defe  jmp     loc_14000DC1A
0x14000df03  mov     eax, [rbp+150h+var_1CC]
0x14000df06  mov     ecx, [r12+130h]
0x14000df0e  mov     [r12+120h], eax
0x14000df16  mov     rax, [rbp+150h+var_188]
0x14000df1a  mov     [r12+128h], rax
0x14000df22  mov     rax, [rbp+150h+var_1C8]
0x14000df26  mov     [rbp+150h+var_1D0], dil
0x14000df2a  cmp     dword ptr [rax+4], 6
0x14000df2e  jz      short loc_14000DF72
0x14000df30  or      ecx, 4
0x14000df33  mov     [r12+130h], ecx
0x14000df3b  mov     rax, cs:WPP_GLOBAL_Control
0x14000df42  lea     r15, WPP_GLOBAL_Control
0x14000df49  mov     [rbp+150h+var_1C8], rax
0x14000df4d  cmp     rax, r15
0x14000df50  jz      loc_14000E107
0x14000df56  cmp     byte ptr [rax+29h], 3
0x14000df5a  jb      loc_14000E107
0x14000df60  bt      dword ptr [rax+2Ch], 9
0x14000df65  jnb     loc_14000E107
0x14000df6b  mov     edx, 19h
0x14000df70  jmp     short loc_14000DFCF
0x14000df72  cmp     [rbp+150h+var_1CC], 2
0x14000df76  jnz     loc_14000E049
0x14000df7c  or      ecx, 4
0x14000df7f  mov     [r12+130h], ecx
0x14000df87  movzx   eax, [rbp+150h+var_126]
0x14000df8b  xor     eax, ecx
0x14000df8d  and     eax, 1
0x14000df90  xor     eax, ecx
0x14000df92  mov     [r12+130h], eax
0x14000df9a  mov     rax, cs:WPP_GLOBAL_Control
0x14000dfa1  lea     r15, WPP_GLOBAL_Control
0x14000dfa8  mov     [rbp+150h+var_1C8], rax
0x14000dfac  cmp     rax, r15
0x14000dfaf  jz      loc_14000E107
0x14000dfb5  cmp     byte ptr [rax+29h], 3
0x14000dfb9  jb      loc_14000E107
0x14000dfbf  bt      dword ptr [rax+2Ch], 9
0x14000dfc4  jnb     loc_14000E107
0x14000dfca  mov     edx, 1Ah
0x14000dfcf  movzx   eax, byte ptr [rbp+150h+var_140+0Fh]
0x14000dfd3  movzx   ecx, byte ptr [rbp+150h+var_140+0Eh]
0x14000dfd7  movzx   r9d, byte ptr [rbp+150h+var_140+0Ch]
0x14000dfdc  movzx   r8d, byte ptr [rbp+150h+var_140+0Dh]
0x14000dfe1  movzx   r10d, byte ptr [rbp+150h+var_140+0Bh]
0x14000dfe6  movzx   r11d, byte ptr [rbp+150h+var_140+0Ah]
0x14000dfeb  movzx   ebx, byte ptr [rbp+150h+var_140+9]
0x14000dfef  movzx   edi, byte ptr [rbp+150h+var_140+8]
0x14000dff3  movzx   esi, word ptr [rbp+150h+var_140+6]
0x14000dff7  movzx   r14d, word ptr [rbp+150h+var_140+4]
0x14000dffc  mov     [rsp+250h+var_1E0], eax
0x14000e000  mov     eax, dword ptr [rbp+150h+var_140]
0x14000e003  mov     [rsp+250h+var_1E8], ecx
0x14000e007  mov     rcx, [rbp+150h+var_1C8]
0x14000e00b  mov     [rsp+250h+var_1F0], r8d
0x14000e010  mov     [rsp+250h+var_1F8], r9d
0x14000e015  mov     r9, r12
0x14000e018  mov     [rsp+250h+var_200], r10d
0x14000e01d  mov     rcx, [rcx+18h]
0x14000e021  mov     dword ptr [rsp+250h+var_208], r11d
0x14000e026  mov     dword ptr [rsp+250h+var_210], ebx
0x14000e02a  mov     dword ptr [rsp+250h+var_218], edi
0x14000e02e  mov     dword ptr [rsp+250h+var_220], esi
0x14000e032  mov     dword ptr [rsp+250h+var_228], r14d
0x14000e037  mov     dword ptr [rsp+250h+var_230], eax
0x14000e03b  call    WPP_SF_qLDDDDDDDDDD
  ... truncated ...
```
