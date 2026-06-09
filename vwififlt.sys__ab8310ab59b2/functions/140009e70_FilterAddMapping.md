# FilterAddMapping

- ea: `0x140009e70`
- end: `0x14000a252`
- name: `FilterAddMapping`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400033f0`

## callees

- `0x140007d00`
- `0x140009270`
- `0x140009e70`
- `0x14000a730`
- `0x14000ada8`
- `0x14000cc68`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000da74`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140009f4d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140009f4d`
- `NDIS!NdisFreeMemory` at `0x14000a1fc`
- `NDIS!NdisFreeMemory` at `0x14000a1fc`
- `NDIS!NdisSetEvent` at `0x14000a1c3`
- `NDIS!NdisSetEvent` at `0x14000a1c3`

## string_xrefs

- `0x140009fd0`: `filterEqualUnicodeString(&UCaseSymbolicLinkName, &pBusIntfInfo->SymbolicName)`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall FilterAddMapping(unsigned int a1, int a2, const UNICODE_STRING *a3)
{
  __int64 v3; // r15
  int v6; // eax
  PVOID v7; // r12
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  USHORT MaximumLength; // ax
  NTSTATUS v11; // edi
  __int64 v12; // r8
  PKDEFERRED_ROUTINE i; // rdx
  _WORD *v14; // rcx
  _QWORD *DeferredContext; // rax
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C v16; // rsi
  __int64 v17; // r8
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C j; // rdx
  char v19; // bl
  PDEVICE_OBJECT *result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  PKDEFERRED_ROUTINE v22; // [rsp+80h] [rbp+40h] BYREF
  PVOID VirtualAddress; // [rsp+88h] [rbp+48h] BYREF

  v3 = a1;
  DestinationString = 0;
  VirtualAddress = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v6 = AllocMem(WPP_MAIN_CB.DeviceExtension, a3->MaximumLength, a3, &VirtualAddress);
  v7 = VirtualAddress;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v9 = 33;
LABEL_8:
      WPP_SF_d(v8->AttachedDevice, v9, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
  }
  else
  {
    MaximumLength = a3->MaximumLength;
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.MaximumLength = MaximumLength;
    DestinationString.Buffer = (PWSTR)VirtualAddress;
    v11 = RtlUpcaseUnicodeString(&DestinationString, a3, 0);
    if ( v11 >= 0 )
    {
      for ( i = WPP_MAIN_CB.Dpc.DeferredRoutine;
            (char *)i != (char *)&WPP_MAIN_CB.Dpc.DeferredRoutine;
            i = *(PKDEFERRED_ROUTINE *)i )
      {
        v22 = i;
        if ( *((_DWORD *)i + 4) == (_DWORD)v3 && *((_DWORD *)i + 5) == a2 )
        {
          if ( !filterEqualUnicodeString((const void **)&DestinationString, (__int64)i + 24) )
            TraceAssert(
              "filterEqualUnicodeString(&UCaseSymbolicLinkName, &pBusIntfInfo->SymbolicName)",
              "onecoreuap\\net\\vwifi\\filter\\filter.c",
              441);
          goto LABEL_28;
        }
      }
      v11 = AllocMem(WPP_MAIN_CB.DeviceExtension, 40, v12, &v22);
      if ( v11 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v9 = 35;
          goto LABEL_8;
        }
        goto LABEL_50;
      }
      v14 = v22;
      *((_QWORD *)v22 + 4) = DestinationString.Buffer;
      v14[12] = DestinationString.Length;
      v14[13] = DestinationString.MaximumLength;
      *((_DWORD *)v14 + 4) = v3;
      *((_DWORD *)v14 + 5) = a2;
      DeferredContext = WPP_MAIN_CB.Dpc.DeferredContext;
      if ( *(struct _DEVICE_OBJECT **)WPP_MAIN_CB.Dpc.DeferredContext != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DeferredRoutine )
        __fastfail(3u);
      *(_QWORD *)v14 = &WPP_MAIN_CB.Dpc.DeferredRoutine;
      *((_QWORD *)v14 + 1) = DeferredContext;
      *DeferredContext = v14;
      WPP_MAIN_CB.Dpc.DeferredContext = v14;
LABEL_28:
      v16 = 0;
      AcquireSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterAddMapping", 469, 0);
      for ( j = WPP_MAIN_CB.DeviceQueue.1;
            ;
            j = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&j )
      {
        v19 = 0;
        if ( *(struct _DEVICE_OBJECT **)&j == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
          break;
        v16 = j;
        if ( ((*(_QWORD *)(*(_QWORD *)&j + 2280LL) >> 24) & 0xFFFFFFLL) == v3
          && *(unsigned __int16 *)(*(_QWORD *)&j + 2286LL) == a2 )
        {
          v19 = 1;
          *(_QWORD *)(*(_QWORD *)&j + 2648LL) = DestinationString.Buffer;
          *(_WORD *)(*(_QWORD *)&j + 2640LL) = DestinationString.Length;
          *(_WORD *)(*(_QWORD *)&j + 2642LL) = DestinationString.MaximumLength;
          break;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 36, v17, (unsigned int)v3, a2);
      if ( v19 )
      {
        if ( !*(_QWORD *)&v16 )
          TraceAssert("pFilter", "onecoreuap\\net\\vwifi\\filter\\filter.c", 498);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_Sdd(WPP_GLOBAL_Control->AttachedDevice, 37, v17, *(_DWORD *)&v16 + 160, v3, a2);
        if ( *(_QWORD *)(*(_QWORD *)&v16 + 2648LL) && *(_BYTE *)(*(_QWORD *)&v16 + 2288LL) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
          }
          NdisSetEvent((PNDIS_EVENT)(*(_QWORD *)&v16 + 2544LL));
        }
      }
      ReleaseSpinLock(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, "FilterAddMapping", 515, 0);
      if ( !v11 )
        goto LABEL_52;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v9 = 34;
        goto LABEL_8;
      }
    }
  }
LABEL_50:
  if ( v7 )
    NdisFreeMemory(v7, 0, 0);
LABEL_52:
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 0x20) != 0 )
      return (PDEVICE_OBJECT *)WPP_SF_d(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 39,
                                 WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140009e70  mov     [rsp-28h+arg_0], rbx
0x140009e75  mov     [rsp-28h+arg_8], rsi
0x140009e7a  push    rbp
0x140009e7b  push    rdi
0x140009e7c  push    r12
0x140009e7e  push    r14
0x140009e80  push    r15
0x140009e82  mov     rbp, rsp
0x140009e85  sub     rsp, 40h
0x140009e89  xorps   xmm0, xmm0
0x140009e8c  mov     r15d, ecx
0x140009e8f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140009e93  mov     rbx, r8
0x140009e96  mov     [rbp+VirtualAddress], 0
0x140009e9e  mov     r14d, edx
0x140009ea1  mov     [rbp+arg_10], 0
0x140009ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x140009eb0  lea     rsi, WPP_GLOBAL_Control
0x140009eb7  cmp     rcx, rsi
0x140009eba  jz      short loc_140009ED8
0x140009ebc  mov     eax, [rcx+2Ch]
0x140009ebf  test    al, 20h
0x140009ec1  jz      short loc_140009ED8
0x140009ec3  mov     rcx, [rcx+18h]
0x140009ec7  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009ece  mov     edx, 20h ; ' '
0x140009ed3  call    WPP_SF_
0x140009ed8  movzx   edx, word ptr [rbx+2]
0x140009edc  lea     r9, [rbp+VirtualAddress]
0x140009ee0  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140009ee7  call    AllocMem
0x140009eec  mov     r12, [rbp+VirtualAddress]
0x140009ef0  mov     edi, eax
0x140009ef2  test    eax, eax
0x140009ef4  jz      short loc_140009F30
0x140009ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x140009efd  cmp     rcx, rsi
0x140009f00  jz      loc_14000A1EF
0x140009f06  mov     edx, [rcx+2Ch]
0x140009f09  mov     bl, 1
0x140009f0b  test    bl, dl
0x140009f0d  jz      loc_14000A1EF
0x140009f13  mov     edx, 21h ; '!'
0x140009f18  mov     r9d, eax
0x140009f1b  mov     rcx, [rcx+18h]
0x140009f1f  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009f26  call    WPP_SF_d
0x140009f2b  jmp     loc_14000A1EF
0x140009f30  movzx   eax, word ptr [rbx+2]
0x140009f34  lea     rcx, [rbp+DestinationString]; DestinationString
0x140009f38  xorps   xmm0, xmm0
0x140009f3b  xor     r8d, r8d; AllocateDestinationString
0x140009f3e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140009f42  mov     rdx, rbx; SourceString
0x140009f45  mov     [rbp+DestinationString.MaximumLength], ax
0x140009f49  mov     [rbp+DestinationString.Buffer], r12
0x140009f4d  call    cs:__imp_RtlUpcaseUnicodeString
0x140009f54  nop     dword ptr [rax+rax+00h]
0x140009f59  mov     edi, eax
0x140009f5b  test    eax, eax
0x140009f5d  jns     short loc_140009F86
0x140009f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f66  cmp     rcx, rsi
0x140009f69  jz      loc_14000A1EF
0x140009f6f  mov     eax, [rcx+2Ch]
0x140009f72  mov     bl, 1
0x140009f74  test    bl, al
0x140009f76  jz      loc_14000A1EF
0x140009f7c  mov     edx, 22h ; '"'
0x140009f81  mov     r9d, edi
0x140009f84  jmp     short loc_140009F1B
0x140009f86  mov     rdx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140009f8d  lea     rbx, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140009f94  cmp     rdx, rbx
0x140009f97  jz      short loc_140009FE1
0x140009f99  mov     [rbp+arg_10], rdx
0x140009f9d  cmp     [rdx+10h], r15d
0x140009fa1  jnz     short loc_140009FA9
0x140009fa3  cmp     [rdx+14h], r14d
0x140009fa7  jz      short loc_140009FAE
0x140009fa9  mov     rdx, [rdx]
0x140009fac  jmp     short loc_140009F94
0x140009fae  add     rdx, 18h
0x140009fb2  lea     rcx, [rbp+DestinationString]
0x140009fb6  call    filterEqualUnicodeString
0x140009fbb  test    al, al
0x140009fbd  jnz     loc_14000A06B
0x140009fc3  mov     r8d, 1B9h
0x140009fc9  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140009fd0  lea     rcx, aFilterequaluni; "filterEqualUnicodeString(&UCaseSymbolic"...
0x140009fd7  call    TraceAssert
0x140009fdc  jmp     loc_14000A06B
0x140009fe1  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140009fe8  lea     r9, [rbp+arg_10]
0x140009fec  mov     edx, 28h ; '('
0x140009ff1  call    AllocMem
0x140009ff6  mov     edi, eax
0x140009ff8  test    eax, eax
0x140009ffa  jz      short loc_14000A023
0x140009ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a003  cmp     rcx, rsi
0x14000a006  jz      loc_14000A1EF
0x14000a00c  mov     eax, [rcx+2Ch]
0x14000a00f  mov     bl, 1
0x14000a011  test    bl, al
0x14000a013  jz      loc_14000A1EF
0x14000a019  mov     edx, 23h ; '#'
0x14000a01e  jmp     loc_140009F81
0x14000a023  mov     rax, [rbp+DestinationString.Buffer]
0x14000a027  mov     rcx, [rbp+arg_10]
0x14000a02b  mov     [rcx+20h], rax
0x14000a02f  movzx   eax, [rbp+DestinationString.Length]
0x14000a033  mov     [rcx+18h], ax
0x14000a037  movzx   eax, [rbp+DestinationString.MaximumLength]
0x14000a03b  mov     [rcx+1Ah], ax
0x14000a03f  mov     [rcx+10h], r15d
0x14000a043  mov     [rcx+14h], r14d
0x14000a047  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredContext
0x14000a04e  cmp     [rax], rbx
0x14000a051  jz      short loc_14000A05A
0x14000a053  mov     ecx, 3
0x14000a058  int     29h; Win8: RtlFailFast(ecx)
0x14000a05a  mov     [rcx], rbx
0x14000a05d  mov     [rcx+8], rax
0x14000a061  mov     [rax], rcx
0x14000a064  mov     cs:WPP_MAIN_CB.Dpc.DeferredContext, rcx
0x14000a06b  xor     esi, esi
0x14000a06d  lea     rdx, aFilteraddmappi; "FilterAddMapping"
0x14000a074  xor     r9d, r9d
0x14000a077  lea     rcx, WPP_MAIN_CB.Queue+10h
0x14000a07e  mov     r8d, 1D5h
0x14000a084  call    AcquireSpinLock
0x14000a089  mov     rdx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000a090  xor     bl, bl
0x14000a092  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x14000a099  cmp     rdx, rax
0x14000a09c  jz      short loc_14000A0EB
0x14000a09e  mov     rcx, [rdx+8E8h]
0x14000a0a5  mov     rsi, rdx
0x14000a0a8  shr     rcx, 18h
0x14000a0ac  and     ecx, 0FFFFFFh
0x14000a0b2  cmp     rcx, r15
0x14000a0b5  jnz     short loc_14000A0C3
0x14000a0b7  movzx   eax, word ptr [rdx+8EEh]
0x14000a0be  cmp     eax, r14d
0x14000a0c1  jz      short loc_14000A0C8
0x14000a0c3  mov     rdx, [rdx]
0x14000a0c6  jmp     short loc_14000A090
0x14000a0c8  mov     rax, [rbp+DestinationString.Buffer]
0x14000a0cc  mov     bl, 1
0x14000a0ce  mov     [rdx+0A58h], rax
0x14000a0d5  movzx   eax, [rbp+DestinationString.Length]
0x14000a0d9  mov     [rdx+0A50h], ax
0x14000a0e0  movzx   eax, [rbp+DestinationString.MaximumLength]
0x14000a0e4  mov     [rdx+0A52h], ax
0x14000a0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0f2  lea     rax, WPP_GLOBAL_Control
0x14000a0f9  cmp     rcx, rax
0x14000a0fc  jz      short loc_14000A11B
0x14000a0fe  mov     eax, [rcx+2Ch]
0x14000a101  test    al, 4
0x14000a103  jz      short loc_14000A11B
0x14000a105  mov     rcx, [rcx+18h]
0x14000a109  mov     edx, 24h ; '$'
0x14000a10e  mov     r9d, r15d
0x14000a111  mov     [rsp+40h+var_20], r14d
0x14000a116  call    WPP_SF_Dd
0x14000a11b  test    bl, bl
0x14000a11d  jz      loc_14000A1CF
0x14000a123  test    rsi, rsi
0x14000a126  jnz     short loc_14000A141
0x14000a128  mov     r8d, 1F2h
0x14000a12e  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000a135  lea     rcx, aPfilter; "pFilter"
0x14000a13c  call    TraceAssert
0x14000a141  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a148  lea     rax, WPP_GLOBAL_Control
0x14000a14f  cmp     rcx, rax
0x14000a152  jz      short loc_14000A181
0x14000a154  mov     eax, [rcx+2Ch]
0x14000a157  test    al, 4
0x14000a159  jz      short loc_14000A17A
0x14000a15b  mov     rcx, [rcx+18h]
0x14000a15f  lea     r9, [rsi+0A0h]
0x14000a166  mov     edx, 25h ; '%'
0x14000a16b  mov     [rsp+40h+var_18], r14d
0x14000a170  mov     [rsp+40h+var_20], r15d
0x14000a175  call    WPP_SF_Sdd
0x14000a17a  lea     rax, WPP_GLOBAL_Control
0x14000a181  cmp     qword ptr [rsi+0A58h], 0
0x14000a189  jz      short loc_14000A1CF
0x14000a18b  cmp     byte ptr [rsi+8F0h], 0
0x14000a192  jz      short loc_14000A1CF
0x14000a194  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a19b  cmp     rcx, rax
0x14000a19e  jz      short loc_14000A1BC
0x14000a1a0  mov     eax, [rcx+2Ch]
0x14000a1a3  test    al, 4
0x14000a1a5  jz      short loc_14000A1BC
0x14000a1a7  mov     rcx, [rcx+18h]
0x14000a1ab  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000a1b2  mov     edx, 26h ; '&'
0x14000a1b7  call    WPP_SF_
0x14000a1bc  lea     rcx, [rsi+9F0h]; Event
0x14000a1c3  call    cs:__imp_NdisSetEvent
0x14000a1ca  nop     dword ptr [rax+rax+00h]
0x14000a1cf  xor     r9d, r9d
0x14000a1d2  lea     rdx, aFilteraddmappi; "FilterAddMapping"
0x14000a1d9  mov     r8d, 203h
0x14000a1df  lea     rcx, WPP_MAIN_CB.Queue+10h
0x14000a1e6  call    ReleaseSpinLock
0x14000a1eb  test    edi, edi
0x14000a1ed  jz      short loc_14000A208
0x14000a1ef  test    r12, r12
0x14000a1f2  jz      short loc_14000A208
0x14000a1f4  xor     r8d, r8d; MemoryFlags
0x14000a1f7  xor     edx, edx; Length
0x14000a1f9  mov     rcx, r12; VirtualAddress
0x14000a1fc  call    cs:__imp_NdisFreeMemory
0x14000a203  nop     dword ptr [rax+rax+00h]
0x14000a208  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a20f  lea     rax, WPP_GLOBAL_Control
0x14000a216  cmp     rcx, rax
0x14000a219  jz      short loc_14000A23A
0x14000a21b  mov     eax, [rcx+2Ch]
0x14000a21e  test    al, 20h
0x14000a220  jz      short loc_14000A23A
0x14000a222  mov     rcx, [rcx+18h]
0x14000a226  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000a22d  mov     edx, 27h ; '''
0x14000a232  mov     r9d, edi
0x14000a235  call    WPP_SF_d
0x14000a23a  mov     rbx, [rsp+40h+arg_0]
0x14000a23f  mov     rsi, [rsp+40h+arg_8]
0x14000a244  add     rsp, 40h
0x14000a248  pop     r15
0x14000a24a  pop     r14
0x14000a24c  pop     r12
0x14000a24e  pop     rdi
0x14000a24f  pop     rbp
0x14000a250  retn
```
