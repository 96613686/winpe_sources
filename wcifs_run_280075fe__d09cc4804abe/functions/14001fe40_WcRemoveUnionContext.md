# WcRemoveUnionContext

- ea: `0x14001fe40`
- end: `0x14002042b`
- name: `WcRemoveUnionContext`
- size: `1515`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140031e40`

## callees

- `0x1400020c4`
- `0x140004198`
- `0x140007c60`
- `0x1400080c0`
- `0x1400142d0`
- `0x14001fe40`
- `0x14002c9dc`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400202c6`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400202c6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400202f1`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400202f1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400200dc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400200dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fec3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fec3`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400202a9`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400202a9`
- `FLTMGR!FltReleaseResource` at `0x14002037a`
- `FLTMGR!FltReleaseResource` at `0x14002037a`
- `FLTMGR!FltObjectDereference` at `0x140020401`
- `FLTMGR!FltObjectDereference` at `0x140020401`
- `FLTMGR!FltReleaseContext` at `0x1400203eb`
- `FLTMGR!FltReleaseContext` at `0x1400203eb`
- `FLTMGR!FltGetInstanceContext` at `0x14002013c`
- `FLTMGR!FltGetInstanceContext` at `0x14002013c`

## pseudocode

```c
__int64 __fastcall WcRemoveUnionContext(__int64 a1, unsigned int a2)
{
  int v4; // edx
  NTSTATUS InstanceContext; // ebx
  int v6; // r9d
  USHORT v7; // cx
  __int64 v8; // rax
  unsigned __int16 *v9; // rdi
  unsigned int v10; // ecx
  WCHAR *v11; // rsi
  USHORT v12; // di
  volatile signed __int32 **v13; // rax
  int v14; // edx
  char v16; // [rsp+30h] [rbp-D0h]
  char v17; // [rsp+38h] [rbp-C8h]
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *Buffer; // [rsp+48h] [rbp-B8h] BYREF
  PFLT_INSTANCE Instance; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING String1; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING InstanceName; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING VolumeName; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int128 v25; // [rsp+98h] [rbp-68h]
  _QWORD v26[34]; // [rsp+B0h] [rbp-50h] BYREF

  Instance = 0;
  Context = 0;
  v25 = 0;
  VolumeName = 0;
  DestinationString = 0;
  String1 = 0;
  InstanceName = 0;
  memset(v26, 0, 0x104u);
  Buffer = (volatile signed __int32 *)v26;
  RtlInitUnicodeString(&DestinationString, L"\\");
  if ( a2 < 0xA0 )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 79;
    v16 = 55;
LABEL_50:
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      11,
      v6,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      v16,
      v17);
    goto LABEL_51;
  }
  if ( *(_DWORD *)(a1 + 4) > a2 )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 80;
    v16 = 62;
    goto LABEL_50;
  }
  if ( *(_DWORD *)a1 != 160 )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 81;
    v16 = 69;
    goto LABEL_50;
  }
  v7 = *(_WORD *)(a1 + 112);
  if ( v7 > 0x64u )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 82;
    v16 = 76;
    goto LABEL_50;
  }
  if ( *(_QWORD *)(a1 + 120) )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 83;
    v16 = 84;
    goto LABEL_50;
  }
  if ( (*(_DWORD *)(a1 + 144) & 1) == 0 )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 84;
    v16 = 91;
    goto LABEL_50;
  }
  v4 = *(unsigned __int16 *)(a1 + 152);
  InstanceName.Buffer = (PWSTR)(a1 + 12);
  v8 = *(unsigned int *)(a1 + 148);
  InstanceName.Length = v7;
  InstanceName.MaximumLength = v7;
  if ( (int)v8 + v4 < (unsigned int)v8 || (int)v8 + v4 > a2 )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 85;
    v16 = 105;
    goto LABEL_50;
  }
  v9 = (unsigned __int16 *)(a1 + v8);
  InstanceContext = WcValidateContainerRootId(a1 + v8);
  if ( InstanceContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = InstanceContext;
    v6 = 86;
    v16 = 114;
    goto LABEL_50;
  }
  v10 = v9[1];
  v11 = v9 + 3;
  VolumeName.Length = v10;
  VolumeName.MaximumLength = v10;
  VolumeName.Buffer = v11;
  v12 = v9[2];
  String1.MaximumLength = v12;
  String1.Length = v12 - v10;
  String1.Buffer = &v11[(unsigned __int64)v10 >> 1];
  if ( RtlEqualUnicodeString(&String1, &DestinationString, 1u) )
  {
    InstanceContext = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = 13;
    v6 = 87;
    v16 = -120;
    goto LABEL_50;
  }
  WcGetInstanceFromVolumeName(&VolumeName, &InstanceName, &Instance);
  InstanceContext = FltGetInstanceContext(Instance, &Context);
  if ( InstanceContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_51;
    v17 = InstanceContext;
    v6 = 88;
    v16 = -109;
    goto LABEL_50;
  }
  if ( *((_DWORD *)Context + 2) == 2 )
  {
    if ( *((_QWORD *)Context + 7) )
    {
      InstanceContext = -1073741637;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_51;
      v17 = -69;
      v6 = 90;
      v16 = -92;
      goto LABEL_50;
    }
    if ( *((_DWORD *)Context + 16) )
    {
      v4 = (int)Context;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)Context + 6, 0, 0) )
      {
        InstanceContext = -1073741637;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_51;
        v17 = -69;
        v6 = 92;
        v16 = -79;
        goto LABEL_50;
      }
      LOWORD(v26[1]) = v12;
      WORD1(v26[1]) = v12;
      HIDWORD(v26[1]) = DWORD1(v25);
      v26[2] = v11;
      FltAcquireResourceExclusive((PERESOURCE)((char *)Context + 72));
      v13 = (volatile signed __int32 **)RtlLookupElementGenericTableAvl(
                                          (PRTL_AVL_TABLE)((char *)Context + 176),
                                          &Buffer);
      if ( v13 )
      {
        Buffer = *v13;
        _InterlockedIncrement(Buffer);
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 176), v13);
        *((_DWORD *)Buffer + 8) |= 0x20u;
        WcReleaseUnionContext(Buffer);
        --*((_DWORD *)Context + 16);
      }
      else
      {
        InstanceContext = -1073741811;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            11,
            93,
            (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
            204,
            13);
        }
      }
      FltReleaseResource((PERESOURCE)((char *)Context + 72));
    }
    else
    {
      InstanceContext = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 4;
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          11,
          91,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          170);
      }
    }
  }
  else
  {
    InstanceContext = -1073741637;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        11,
        89,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        153);
    }
  }
LABEL_51:
  if ( Context )
    FltReleaseContext(Context);
  if ( Instance )
    FltObjectDereference(Instance);
  return (unsigned int)InstanceContext;
}

```

## disassembly

```asm
0x14001fe40  push    rbp
0x14001fe42  push    rbx
0x14001fe43  push    rsi
0x14001fe44  push    rdi
0x14001fe45  lea     rbp, [rsp-0D8h]
0x14001fe4d  sub     rsp, 1D8h
0x14001fe54  mov     rax, cs:__security_cookie
0x14001fe5b  xor     rax, rsp
0x14001fe5e  mov     [rbp+0F0h+var_30], rax
0x14001fe65  xorps   xmm0, xmm0
0x14001fe68  mov     [rsp+1F0h+Instance], 0
0x14001fe71  xorps   xmm1, xmm1
0x14001fe74  mov     [rsp+1F0h+Context], 0
0x14001fe7d  mov     edi, edx
0x14001fe7f  mov     rbx, rcx
0x14001fe82  xor     eax, eax
0x14001fe84  lea     rcx, [rbp+0F0h+var_140]; void *
0x14001fe88  xor     edx, edx; Val
0x14001fe8a  mov     [rbp+0F0h+var_13C], eax
0x14001fe8d  mov     r8d, 104h; Size
0x14001fe93  movups  [rbp+0F0h+var_158], xmm0
0x14001fe97  movups  xmmword ptr [rsp+1F0h+VolumeName.Length], xmm1
0x14001fe9c  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x14001fea0  movups  xmmword ptr [rsp+1F0h+String1.Length], xmm1
0x14001fea5  movups  xmmword ptr [rsp+1F0h+InstanceName.Length], xmm0
0x14001feaa  call    memset
0x14001feaf  lea     rax, [rbp+0F0h+var_140]
0x14001feb3  lea     rdx, Source2; "\\"
0x14001feba  mov     [rsp+1F0h+Buffer], rax
0x14001febf  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x14001fec3  call    cs:__imp_RtlInitUnicodeString
0x14001feca  nop     dword ptr [rax+rax+00h]
0x14001fecf  mov     eax, 0A0h
0x14001fed4  cmp     edi, eax
0x14001fed6  jnb     short loc_14001FF0A
0x14001fed8  mov     ecx, 0C000000Dh
0x14001fedd  mov     ebx, ecx
0x14001fedf  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fee6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001feed  jz      loc_1400203E1
0x14001fef3  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x14001fef7  mov     r9d, 4Fh ; 'O'
0x14001fefd  mov     dword ptr [rsp+1F0h+var_1C0], 737h
0x14001ff05  jmp     loc_1400203B1
0x14001ff0a  cmp     [rbx+4], edi
0x14001ff0d  jbe     short loc_14001FF41
0x14001ff0f  mov     ecx, 0C000000Dh
0x14001ff14  mov     ebx, ecx
0x14001ff16  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ff1d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ff24  jz      loc_1400203E1
0x14001ff2a  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x14001ff2e  mov     r9d, 50h ; 'P'
0x14001ff34  mov     dword ptr [rsp+1F0h+var_1C0], 73Eh
0x14001ff3c  jmp     loc_1400203B1
0x14001ff41  cmp     [rbx], eax
0x14001ff43  jz      short loc_14001FF77
0x14001ff45  mov     ecx, 0C000000Dh
0x14001ff4a  mov     ebx, ecx
0x14001ff4c  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ff53  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ff5a  jz      loc_1400203E1
0x14001ff60  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x14001ff64  mov     r9d, 51h ; 'Q'
0x14001ff6a  mov     dword ptr [rsp+1F0h+var_1C0], 745h
0x14001ff72  jmp     loc_1400203B1
0x14001ff77  movzx   ecx, word ptr [rbx+70h]
0x14001ff7b  cmp     cx, 64h ; 'd'
0x14001ff7f  jbe     short loc_14001FFB3
0x14001ff81  mov     ecx, 0C000000Dh
0x14001ff86  mov     ebx, ecx
0x14001ff88  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ff8f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ff96  jz      loc_1400203E1
0x14001ff9c  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x14001ffa0  mov     r9d, 52h ; 'R'
0x14001ffa6  mov     dword ptr [rsp+1F0h+var_1C0], 74Ch
0x14001ffae  jmp     loc_1400203B1
0x14001ffb3  cmp     qword ptr [rbx+78h], 0
0x14001ffb8  jz      short loc_14001FFEC
0x14001ffba  mov     ecx, 0C000000Dh
0x14001ffbf  mov     ebx, ecx
0x14001ffc1  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ffc8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ffcf  jz      loc_1400203E1
0x14001ffd5  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x14001ffd9  mov     r9d, 53h ; 'S'
0x14001ffdf  mov     dword ptr [rsp+1F0h+var_1C0], 754h
0x14001ffe7  jmp     loc_1400203B1
0x14001ffec  mov     eax, [rbx+90h]
0x14001fff2  test    al, 1
0x14001fff4  jnz     short loc_140020028
0x14001fff6  mov     ecx, 0C000000Dh
0x14001fffb  mov     ebx, ecx
0x14001fffd  lea     rax, WPP_RECORDER_INITIALIZED
0x140020004  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002000b  jz      loc_1400203E1
0x140020011  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x140020015  mov     r9d, 54h ; 'T'
0x14002001b  mov     dword ptr [rsp+1F0h+var_1C0], 75Bh
0x140020023  jmp     loc_1400203B1
0x140020028  movzx   edx, word ptr [rbx+98h]
0x14002002f  lea     rax, [rbx+0Ch]
0x140020033  mov     [rsp+1F0h+InstanceName.Buffer], rax
0x140020038  mov     eax, [rbx+94h]
0x14002003e  mov     [rsp+1F0h+InstanceName.Length], cx
0x140020043  mov     [rsp+1F0h+InstanceName.MaximumLength], cx
0x140020048  lea     ecx, [rax+rdx]
0x14002004b  cmp     ecx, eax
0x14002004d  jb      loc_140020388
0x140020053  cmp     ecx, edi
0x140020055  ja      loc_140020388
0x14002005b  lea     rdi, [rbx+rax]
0x14002005f  mov     rcx, rdi
0x140020062  call    WcValidateContainerRootId
0x140020067  mov     ebx, eax
0x140020069  test    eax, eax
0x14002006b  jns     short loc_140020098
0x14002006d  lea     rax, WPP_RECORDER_INITIALIZED
0x140020074  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002007b  jz      loc_1400203E1
0x140020081  mov     dword ptr [rsp+1F0h+var_1B8], ebx
0x140020085  mov     r9d, 56h ; 'V'
0x14002008b  mov     dword ptr [rsp+1F0h+var_1C0], 772h
0x140020093  jmp     loc_1400203B1
0x140020098  movzx   ecx, word ptr [rdi+2]
0x14002009c  lea     rsi, [rdi+6]
0x1400200a0  mov     [rsp+1F0h+VolumeName.Length], cx
0x1400200a5  lea     rdx, [rbp+0F0h+DestinationString]; String2
0x1400200a9  mov     [rsp+1F0h+VolumeName.MaximumLength], cx
0x1400200ae  mov     r8b, 1; CaseInSensitive
0x1400200b1  mov     [rbp+0F0h+VolumeName.Buffer], rsi
0x1400200b5  movzx   edi, word ptr [rdi+4]
0x1400200b9  movzx   eax, di
0x1400200bc  mov     [rsp+1F0h+String1.MaximumLength], di
0x1400200c1  sub     ax, cx
0x1400200c4  mov     [rsp+1F0h+String1.Length], ax
0x1400200c9  mov     eax, ecx
0x1400200cb  shr     rax, 1
0x1400200ce  lea     rcx, [rsp+1F0h+String1]; String1
0x1400200d3  lea     rax, [rsi+rax*2]
0x1400200d7  mov     [rsp+1F0h+String1.Buffer], rax
0x1400200dc  call    cs:__imp_RtlEqualUnicodeString
0x1400200e3  nop     dword ptr [rax+rax+00h]
0x1400200e8  test    al, al
0x1400200ea  jz      short loc_14002011E
0x1400200ec  mov     ecx, 0C000000Dh
0x1400200f1  mov     ebx, ecx
0x1400200f3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400200fa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020101  jz      loc_1400203E1
0x140020107  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x14002010b  mov     r9d, 57h ; 'W'
0x140020111  mov     dword ptr [rsp+1F0h+var_1C0], 788h
0x140020119  jmp     loc_1400203B1
0x14002011e  lea     r8, [rsp+1F0h+Instance]; RetInstance
0x140020123  lea     rdx, [rsp+1F0h+InstanceName]; InstanceName
0x140020128  lea     rcx, [rsp+1F0h+VolumeName]; VolumeName
0x14002012d  call    WcGetInstanceFromVolumeName
0x140020132  mov     rcx, [rsp+1F0h+Instance]; Instance
0x140020137  lea     rdx, [rsp+1F0h+Context]; Context
0x14002013c  call    cs:__imp_FltGetInstanceContext
0x140020143  nop     dword ptr [rax+rax+00h]
0x140020148  mov     ebx, eax
0x14002014a  test    eax, eax
0x14002014c  jns     short loc_140020179
0x14002014e  lea     rax, WPP_RECORDER_INITIALIZED
0x140020155  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002015c  jz      loc_1400203E1
0x140020162  mov     dword ptr [rsp+1F0h+var_1B8], ebx
0x140020166  mov     r9d, 58h ; 'X'
0x14002016c  mov     dword ptr [rsp+1F0h+var_1C0], 793h
0x140020174  jmp     loc_1400203B1
0x140020179  mov     rax, [rsp+1F0h+Context]
0x14002017e  cmp     dword ptr [rax+8], 2
0x140020182  jz      short loc_1400201E0
0x140020184  mov     ebx, 0C00000BBh
0x140020189  lea     rax, WPP_RECORDER_INITIALIZED
0x140020190  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020197  jz      loc_1400203E1
0x14002019d  mov     r9d, 59h ; 'Y'
0x1400201a3  mov     dword ptr [rsp+1F0h+var_1C0], 799h
0x1400201ab  mov     dl, 2
0x1400201ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400201b4  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x1400201bb  mov     [rsp+1F0h+var_1C8], rax
0x1400201c0  mov     r8d, 0Bh
0x1400201c6  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x1400201cd  mov     [rsp+1F0h+var_1D0], rax
0x1400201d2  mov     rcx, [rcx+40h]
0x1400201d6  call    WPP_RECORDER_SF_sD
0x1400201db  jmp     loc_1400203E1
0x1400201e0  mov     rax, [rsp+1F0h+Context]
0x1400201e5  cmp     qword ptr [rax+38h], 0
0x1400201ea  jz      short loc_14002021C
0x1400201ec  mov     ebx, 0C00000BBh
0x1400201f1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400201f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400201ff  jz      loc_1400203E1
0x140020205  mov     dword ptr [rsp+1F0h+var_1B8], ebx
0x140020209  mov     r9d, 5Ah ; 'Z'
0x14002020f  mov     dword ptr [rsp+1F0h+var_1C0], 7A4h
0x140020217  jmp     loc_1400203B1
0x14002021c  mov     rax, [rsp+1F0h+Context]
0x140020221  cmp     dword ptr [rax+40h], 0
0x140020225  jnz     short loc_140020250
0x140020227  xor     ebx, ebx
0x140020229  lea     rax, WPP_RECORDER_INITIALIZED
0x140020230  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020237  jz      loc_1400203E1
0x14002023d  lea     r9d, [rbx+5Bh]
0x140020241  mov     dword ptr [rsp+1F0h+var_1C0], 7AAh
0x140020249  mov     dl, 4
0x14002024b  jmp     loc_1400201AD
0x140020250  mov     rdx, [rsp+1F0h+Context]
0x140020255  xor     ecx, ecx
0x140020257  xor     eax, eax
0x140020259  lock cmpxchg [rdx+18h], ecx
0x14002025e  jz      short loc_14002028E
0x140020260  mov     ebx, 0C00000BBh
0x140020265  lea     rax, WPP_RECORDER_INITIALIZED
0x14002026c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020273  jz      loc_1400203E1
0x140020279  mov     dword ptr [rsp+1F0h+var_1B8], ebx
0x14002027d  lea     r9d, [rcx+5Ch]
0x140020281  mov     dword ptr [rsp+1F0h+var_1C0], 7B1h
0x140020289  jmp     loc_1400203B1
0x14002028e  mov     rcx, [rsp+1F0h+Context]
0x140020293  mov     eax, dword ptr [rbp+0F0h+var_158+4]
0x140020296  add     rcx, 48h ; 'H'; Resource
0x14002029a  mov     [rbp+0F0h+var_138], di
0x14002029e  mov     [rbp+0F0h+var_136], di
0x1400202a2  mov     [rbp+0F0h+var_134], eax
0x1400202a5  mov     [rbp+0F0h+var_130], rsi
0x1400202a9  call    cs:__imp_FltAcquireResourceExclusive
0x1400202b0  nop     dword ptr [rax+rax+00h]
0x1400202b5  mov     rcx, [rsp+1F0h+Context]
0x1400202ba  lea     rdx, [rsp+1F0h+Buffer]; Buffer
0x1400202bf  add     rcx, 0B0h; Table
0x1400202c6  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400202cd  nop     dword ptr [rax+rax+00h]
0x1400202d2  test    rax, rax
0x1400202d5  jz      short loc_14002031A
0x1400202d7  mov     rcx, [rax]
0x1400202da  mov     [rsp+1F0h+Buffer], rcx
0x1400202df  lock inc dword ptr [rcx]
0x1400202e2  mov     rcx, [rsp+1F0h+Context]
0x1400202e7  mov     rdx, rax; Buffer
0x1400202ea  add     rcx, 0B0h; Table
0x1400202f1  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400202f8  nop     dword ptr [rax+rax+00h]
0x1400202fd  mov     rax, [rsp+1F0h+Buffer]
0x140020302  or      dword ptr [rax+20h], 20h
0x140020306  mov     rcx, [rsp+1F0h+Buffer]
0x14002030b  call    WcReleaseUnionContext
0x140020310  mov     rax, [rsp+1F0h+Context]
0x140020315  dec     dword ptr [rax+40h]
0x140020318  jmp     short loc_140020371
0x14002031a  mov     ecx, 0C000000Dh
0x14002031f  mov     ebx, ecx
0x140020321  lea     rax, WPP_RECORDER_INITIALIZED
0x140020328  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002032f  jz      short loc_140020371
0x140020331  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x140020335  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002033c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020343  mov     r9d, 5Dh ; ']'
0x140020349  mov     dword ptr [rsp+1F0h+var_1C0], 7CCh
0x140020351  mov     dl, 2
0x140020353  mov     [rsp+1F0h+var_1C8], rax
0x140020358  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002035f  mov     [rsp+1F0h+var_1D0], rax
0x140020364  mov     rcx, [rcx+40h]
0x140020368  lea     r8d, [r9-52h]
0x14002036c  call    WPP_RECORDER_SF_sDd
0x140020371  mov     rcx, [rsp+1F0h+Context]
0x140020376  add     rcx, 48h ; 'H'; Resource
0x14002037a  call    cs:__imp_FltReleaseResource
0x140020381  nop     dword ptr [rax+rax+00h]
0x140020386  jmp     short loc_1400203E1
0x140020388  mov     ecx, 0C000000Dh
0x14002038d  mov     ebx, ecx
0x14002038f  lea     rax, WPP_RECORDER_INITIALIZED
0x140020396  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002039d  jz      short loc_1400203E1
0x14002039f  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x1400203a3  mov     r9d, 55h ; 'U'
0x1400203a9  mov     dword ptr [rsp+1F0h+var_1C0], 769h
0x1400203b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400203b8  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x1400203bf  mov     [rsp+1F0h+var_1C8], rax
0x1400203c4  mov     r8d, 0Bh
0x1400203ca  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x1400203d1  mov     dl, 2
0x1400203d3  mov     [rsp+1F0h+var_1D0], rax
0x1400203d8  mov     rcx, [rcx+40h]
0x1400203dc  call    WPP_RECORDER_SF_sDd
0x1400203e1  mov     rcx, [rsp+1F0h+Context]; Context
0x1400203e6  test    rcx, rcx
0x1400203e9  jz      short loc_1400203F7
  ... truncated ...
```
