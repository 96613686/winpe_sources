# MpFreeCommPorts

- ea: `0x14007a060`
- end: `0x14007a254`
- name: `MpFreeCommPorts`
- size: `500`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14007bef0`
- `0x14008e860`
- `0x14008f314`

## callees

- `0x14007a060`

## import_xrefs

- `FLTMGR!FltCloseCommunicationPort` at `0x14007a077`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a0a8`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a0d9`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a10a`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a13b`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a16c`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a19d`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a1ce`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a1ff`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a230`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a077`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a0a8`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a0d9`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a10a`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a13b`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a16c`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a19d`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a1ce`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a1ff`
- `FLTMGR!FltCloseCommunicationPort` at `0x14007a230`

## pseudocode

```c
ULONG_PTR MpFreeCommPorts()
{
  struct _FLT_PORT *v0; // rcx
  struct _FLT_PORT *v1; // rcx
  struct _FLT_PORT *v2; // rcx
  struct _FLT_PORT *v3; // rcx
  struct _FLT_PORT *v4; // rcx
  struct _FLT_PORT *v5; // rcx
  struct _FLT_PORT *v6; // rcx
  struct _FLT_PORT *v7; // rcx
  struct _FLT_PORT *v8; // rcx
  ULONG_PTR result; // rax
  struct _FLT_PORT *v10; // rcx

  v0 = *(struct _FLT_PORT **)(MpData + 408);
  if ( v0 )
  {
    FltCloseCommunicationPort(v0);
    *(_QWORD *)(MpData + 408) = 0;
  }
  v1 = *(struct _FLT_PORT **)(MpData + 312);
  if ( v1 )
  {
    FltCloseCommunicationPort(v1);
    *(_QWORD *)(MpData + 312) = 0;
  }
  v2 = *(struct _FLT_PORT **)(MpData + 344);
  if ( v2 )
  {
    FltCloseCommunicationPort(v2);
    *(_QWORD *)(MpData + 344) = 0;
  }
  v3 = *(struct _FLT_PORT **)(MpData + 376);
  if ( v3 )
  {
    FltCloseCommunicationPort(v3);
    *(_QWORD *)(MpData + 376) = 0;
  }
  v4 = *(struct _FLT_PORT **)(MpData + 280);
  if ( v4 )
  {
    FltCloseCommunicationPort(v4);
    *(_QWORD *)(MpData + 280) = 0;
  }
  v5 = *(struct _FLT_PORT **)(MpData + 424);
  if ( v5 )
  {
    FltCloseCommunicationPort(v5);
    *(_QWORD *)(MpData + 424) = 0;
  }
  v6 = *(struct _FLT_PORT **)(MpData + 328);
  if ( v6 )
  {
    FltCloseCommunicationPort(v6);
    *(_QWORD *)(MpData + 328) = 0;
  }
  v7 = *(struct _FLT_PORT **)(MpData + 360);
  if ( v7 )
  {
    FltCloseCommunicationPort(v7);
    *(_QWORD *)(MpData + 360) = 0;
  }
  v8 = *(struct _FLT_PORT **)(MpData + 392);
  if ( v8 )
  {
    FltCloseCommunicationPort(v8);
    *(_QWORD *)(MpData + 392) = 0;
  }
  result = MpData;
  v10 = *(struct _FLT_PORT **)(MpData + 296);
  if ( v10 )
  {
    FltCloseCommunicationPort(v10);
    result = MpData;
    *(_QWORD *)(MpData + 296) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14007a060  sub     rsp, 28h
0x14007a064  mov     rax, cs:MpData
0x14007a06b  mov     rcx, [rax+198h]; ServerPort
0x14007a072  test    rcx, rcx
0x14007a075  jz      short loc_14007A095
0x14007a077  call    cs:__imp_FltCloseCommunicationPort
0x14007a07e  nop     dword ptr [rax+rax+00h]
0x14007a083  mov     rax, cs:MpData
0x14007a08a  mov     qword ptr [rax+198h], 0
0x14007a095  mov     rax, cs:MpData
0x14007a09c  mov     rcx, [rax+138h]; ServerPort
0x14007a0a3  test    rcx, rcx
0x14007a0a6  jz      short loc_14007A0C6
0x14007a0a8  call    cs:__imp_FltCloseCommunicationPort
0x14007a0af  nop     dword ptr [rax+rax+00h]
0x14007a0b4  mov     rax, cs:MpData
0x14007a0bb  mov     qword ptr [rax+138h], 0
0x14007a0c6  mov     rax, cs:MpData
0x14007a0cd  mov     rcx, [rax+158h]; ServerPort
0x14007a0d4  test    rcx, rcx
0x14007a0d7  jz      short loc_14007A0F7
0x14007a0d9  call    cs:__imp_FltCloseCommunicationPort
0x14007a0e0  nop     dword ptr [rax+rax+00h]
0x14007a0e5  mov     rax, cs:MpData
0x14007a0ec  mov     qword ptr [rax+158h], 0
0x14007a0f7  mov     rax, cs:MpData
0x14007a0fe  mov     rcx, [rax+178h]; ServerPort
0x14007a105  test    rcx, rcx
0x14007a108  jz      short loc_14007A128
0x14007a10a  call    cs:__imp_FltCloseCommunicationPort
0x14007a111  nop     dword ptr [rax+rax+00h]
0x14007a116  mov     rax, cs:MpData
0x14007a11d  mov     qword ptr [rax+178h], 0
0x14007a128  mov     rax, cs:MpData
0x14007a12f  mov     rcx, [rax+118h]; ServerPort
0x14007a136  test    rcx, rcx
0x14007a139  jz      short loc_14007A159
0x14007a13b  call    cs:__imp_FltCloseCommunicationPort
0x14007a142  nop     dword ptr [rax+rax+00h]
0x14007a147  mov     rax, cs:MpData
0x14007a14e  mov     qword ptr [rax+118h], 0
0x14007a159  mov     rax, cs:MpData
0x14007a160  mov     rcx, [rax+1A8h]; ServerPort
0x14007a167  test    rcx, rcx
0x14007a16a  jz      short loc_14007A18A
0x14007a16c  call    cs:__imp_FltCloseCommunicationPort
0x14007a173  nop     dword ptr [rax+rax+00h]
0x14007a178  mov     rax, cs:MpData
0x14007a17f  mov     qword ptr [rax+1A8h], 0
0x14007a18a  mov     rax, cs:MpData
0x14007a191  mov     rcx, [rax+148h]; ServerPort
0x14007a198  test    rcx, rcx
0x14007a19b  jz      short loc_14007A1BB
0x14007a19d  call    cs:__imp_FltCloseCommunicationPort
0x14007a1a4  nop     dword ptr [rax+rax+00h]
0x14007a1a9  mov     rax, cs:MpData
0x14007a1b0  mov     qword ptr [rax+148h], 0
0x14007a1bb  mov     rax, cs:MpData
0x14007a1c2  mov     rcx, [rax+168h]; ServerPort
0x14007a1c9  test    rcx, rcx
0x14007a1cc  jz      short loc_14007A1EC
0x14007a1ce  call    cs:__imp_FltCloseCommunicationPort
0x14007a1d5  nop     dword ptr [rax+rax+00h]
0x14007a1da  mov     rax, cs:MpData
0x14007a1e1  mov     qword ptr [rax+168h], 0
0x14007a1ec  mov     rax, cs:MpData
0x14007a1f3  mov     rcx, [rax+188h]; ServerPort
0x14007a1fa  test    rcx, rcx
0x14007a1fd  jz      short loc_14007A21D
0x14007a1ff  call    cs:__imp_FltCloseCommunicationPort
0x14007a206  nop     dword ptr [rax+rax+00h]
0x14007a20b  mov     rax, cs:MpData
0x14007a212  mov     qword ptr [rax+188h], 0
0x14007a21d  mov     rax, cs:MpData
0x14007a224  mov     rcx, [rax+128h]; ServerPort
0x14007a22b  test    rcx, rcx
0x14007a22e  jz      short loc_14007A24E
0x14007a230  call    cs:__imp_FltCloseCommunicationPort
0x14007a237  nop     dword ptr [rax+rax+00h]
0x14007a23c  mov     rax, cs:MpData
0x14007a243  mov     qword ptr [rax+128h], 0
0x14007a24e  add     rsp, 28h
0x14007a252  retn
```
