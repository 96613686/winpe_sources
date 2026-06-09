# VmsOmpObjectAllocate

- ea: `0x140077bd0`
- end: `0x140077f1c`
- name: `VmsOmpObjectAllocate`
- size: `844`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING SourceString, PCUNICODE_STRING, PCUNICODE_STRING, __int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007f3c0`
- `0x1400fb990`
- `0x1400fe920`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x14003a450`
- `0x140066bec`
- `0x140077bd0`
- `0x14008497c`
- `0x14009128c`
- `0x140109ac8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140077d84`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077db6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077ded`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077d84`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077db6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140077ded`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077e04`
- `ntoskrnl!KeInitializeSpinLock` at `0x140077e04`
- `ntoskrnl!ExAllocatePool2` at `0x140077c48`
- `ntoskrnl!ExAllocatePool2` at `0x140077c48`
- `NDIS!NdisAllocateRefCount` at `0x140077e20`
- `NDIS!NdisAllocateRefCount` at `0x140077e20`
- `NDIS!NdisAllocateRWLock` at `0x140077e53`
- `NDIS!NdisAllocateRWLock` at `0x140077e53`

## pseudocode

```c
__int64 __fastcall VmsOmpObjectAllocate(
        unsigned int a1,
        __int16 a2,
        int a3,
        char a4,
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING a6,
        PCUNICODE_STRING a7,
        __int64 a8,
        __int64 *a9)
{
  char v9; // bp
  unsigned int v12; // ebx
  __int64 Pool2; // rax
  int v14; // edx
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  unsigned int v19; // edi
  __int64 v20; // rbx
  int Length; // edx
  int v22; // r9d
  unsigned __int16 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 RefCount; // rax
  NDIS_HANDLE v27; // rcx
  PNDIS_RW_LOCK_EX RWLock; // rax
  int v29; // edx
  __int64 result; // rax
  __int64 v31; // [rsp+20h] [rbp-88h]
  char v32; // [rsp+28h] [rbp-80h]
  char v33; // [rsp+30h] [rbp-78h]

  v9 = a2;
  if ( a1 < 0x4D0 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      42,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      (__int64)"ObjSize >= sizeof(VMS_OBJ_HDR)");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( v9 )
    v12 = a1 + VmsCacheLineSizeInBytes - 1;
  else
    v12 = a1;
  Pool2 = ExAllocatePool2(64, v12, 1649374038);
  if ( !Pool2 )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v14, 20, 43, (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids, v12);
    v19 = -1073741670;
LABEL_27:
    WPP_RECORDER_SF_DlLZZZd(v16, v15, v17, v18, v31, a1, v9, a3, (__int64)SourceString, (__int64)a6, (__int64)a7, v19);
    v20 = 0;
    goto LABEL_28;
  }
  if ( v9 )
    v20 = ~((unsigned int)VmsCacheLineSizeInBytes - 1LL) & (Pool2 + (unsigned int)VmsCacheLineSizeInBytes - 1LL);
  else
    v20 = Pool2;
  *(_QWORD *)(v20 + 1216) = Pool2;
  Length = SourceString->Length;
  if ( (unsigned __int16)(Length - 1) > 0xFDu )
  {
    v19 = -1073741773;
    v33 = 51;
    v22 = 44;
    v32 = SourceString->Length;
    goto LABEL_25;
  }
  if ( a7 && a7->Length > 0x1FEu )
  {
    v19 = -1073741811;
    v33 = 13;
    v22 = 45;
    v32 = a7->Length;
LABEL_25:
    LOBYTE(Length) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, Length, 20, v22, (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids, v32, v33);
    goto LABEL_26;
  }
  v23 = 0;
  LOWORD(Length) = (unsigned __int16)Length >> 1;
  while ( v23 < (unsigned __int16)Length )
  {
    if ( SourceString->Buffer[v23] == 92 )
    {
      v19 = -1073741773;
      LOBYTE(Length) = 2;
      WPP_RECORDER_SF_Zd(
        VmsIfrLog,
        Length,
        20,
        46,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)SourceString,
        51);
      goto LABEL_26;
    }
    ++v23;
  }
  *(_WORD *)(v20 + 74) = 256;
  *(_QWORD *)(v20 + 80) = v20 + 88;
  *(_WORD *)(v20 + 72) = 0;
  v19 = 0;
  RtlCopyUnicodeString((PUNICODE_STRING)(v20 + 72), SourceString);
  *(_WORD *)(v20 + 346) = 256;
  *(_QWORD *)(v20 + 352) = v20 + 360;
  *(_WORD *)(v20 + 344) = 0;
  RtlCopyUnicodeString((PUNICODE_STRING)(v20 + 344), a6);
  *(_WORD *)(v20 + 618) = 512;
  *(_QWORD *)(v20 + 624) = v20 + 632;
  *(_WORD *)(v20 + 616) = 0;
  if ( a7 )
    RtlCopyUnicodeString((PUNICODE_STRING)(v20 + 616), a7);
  *(_DWORD *)(v20 + 64) = a3;
  *(_DWORD *)(v20 + 68) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(v20 + 32));
  LOBYTE(v24) = a4;
  LOBYTE(v25) = 2;
  *(_DWORD *)(v20 + 40) = 1;
  RefCount = NdisAllocateRefCount(v24, v25);
  v27 = VmsMiniportHandle;
  *(_QWORD *)(v20 + 48) = RefCount;
  *(_QWORD *)(v20 + 1208) = a8;
  *(_DWORD *)(v20 + 1224) = 0;
  *(_BYTE *)(v20 + 1228) = 1;
  RWLock = NdisAllocateRWLock(v27);
  *(_QWORD *)(v20 + 56) = RWLock;
  if ( !RWLock )
  {
    v19 = -1073741670;
    LOBYTE(v29) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v29, 20, 48, (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids, 154);
LABEL_26:
    VmsOmpObjectCleanup(v20);
    goto LABEL_27;
  }
LABEL_28:
  result = v19;
  *a9 = v20;
  return result;
}

```

## disassembly

```asm
0x140077bd0  mov     [rsp+arg_18], r9b
0x140077bd5  push    rbx
0x140077bd6  push    rbp
0x140077bd7  push    rsi
0x140077bd8  push    rdi
0x140077bd9  push    r12
0x140077bdb  push    r13
0x140077bdd  push    r14
0x140077bdf  push    r15
0x140077be1  sub     rsp, 68h
0x140077be5  movzx   ebp, dl
0x140077be8  mov     r12d, r8d
0x140077beb  lea     rdi, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140077bf2  mov     esi, ecx
0x140077bf4  cmp     ecx, 4D0h
0x140077bfa  jnb     short loc_140077C28
0x140077bfc  mov     rcx, cs:VmsIfrLog
0x140077c03  lea     rax, aObjsizeSizeofV; "ObjSize >= sizeof(VMS_OBJ_HDR)"
0x140077c0a  mov     r9d, 2Ah ; '*'
0x140077c10  mov     [rsp+0A8h+var_80], rax
0x140077c15  mov     [rsp+0A8h+var_88], rdi
0x140077c1a  lea     r8d, [r9-17h]
0x140077c1e  call    WPP_RECORDER_SF_s
0x140077c23  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjSize >= sizeof(VMS_OBJ_HDR)")
0x140077c28  test    bpl, bpl
0x140077c2b  jz      short loc_140077C39
0x140077c2d  mov     ebx, cs:VmsCacheLineSizeInBytes
0x140077c33  dec     ebx
0x140077c35  add     ebx, esi
0x140077c37  jmp     short loc_140077C3B
0x140077c39  mov     ebx, esi
0x140077c3b  mov     edx, ebx
0x140077c3d  mov     ecx, 40h ; '@'
0x140077c42  mov     r8d, 624F7356h
0x140077c48  call    cs:__imp_ExAllocatePool2
0x140077c4f  nop     dword ptr [rax+rax+00h]
0x140077c54  mov     r14, [rsp+0A8h+arg_30]
0x140077c5c  mov     rcx, rax
0x140077c5f  mov     r13, [rsp+0A8h+arg_28]
0x140077c67  mov     r15, [rsp+0A8h+SourceString]
0x140077c6f  test    rax, rax
0x140077c72  jnz     short loc_140077C9D
0x140077c74  mov     rcx, cs:VmsIfrLog
0x140077c7b  lea     r9d, [rax+2Bh]
0x140077c7f  mov     dword ptr [rsp+0A8h+var_80], ebx
0x140077c83  lea     r8d, [rax+14h]
0x140077c87  mov     dl, 2
0x140077c89  mov     [rsp+0A8h+var_88], rdi
0x140077c8e  call    WPP_RECORDER_SF_d
0x140077c93  mov     edi, 0C000009Ah
0x140077c98  jmp     loc_140077ED6
0x140077c9d  test    bpl, bpl
0x140077ca0  jz      short loc_140077CBA
0x140077ca2  mov     eax, cs:VmsCacheLineSizeInBytes
0x140077ca8  lea     rbx, [rax-1]
0x140077cac  add     rbx, rcx
0x140077caf  dec     rax
0x140077cb2  not     rax
0x140077cb5  and     rbx, rax
0x140077cb8  jmp     short loc_140077CBD
0x140077cba  mov     rbx, rcx
0x140077cbd  mov     [rbx+4C0h], rcx
0x140077cc4  mov     r9d, 1
0x140077cca  movzx   edx, word ptr [r15]
0x140077cce  mov     ecx, 0FDh
0x140077cd3  movzx   eax, dx
0x140077cd6  sub     ax, r9w
0x140077cda  cmp     ax, cx
0x140077cdd  ja      loc_140077E99
0x140077ce3  test    r14, r14
0x140077ce6  jz      short loc_140077D0E
0x140077ce8  movzx   eax, word ptr [r14]
0x140077cec  mov     ecx, 1FEh
0x140077cf1  cmp     ax, cx
0x140077cf4  jbe     short loc_140077D0E
0x140077cf6  mov     edi, 0C000000Dh
0x140077cfb  mov     dword ptr [rsp+0A8h+var_78], edi
0x140077cff  mov     r9d, 2Dh ; '-'
0x140077d05  mov     dword ptr [rsp+0A8h+var_80], eax
0x140077d09  jmp     loc_140077EAE
0x140077d0e  xor     r8d, r8d
0x140077d11  shr     dx, 1
0x140077d14  cmp     r8w, dx
0x140077d18  jnb     short loc_140077D68
0x140077d1a  mov     rax, [r15+8]
0x140077d1e  movzx   ecx, r8w
0x140077d22  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140077d27  jz      short loc_140077D2F
0x140077d29  add     r8w, r9w
0x140077d2d  jmp     short loc_140077D14
0x140077d2f  mov     ecx, 0C0000033h
0x140077d34  mov     edi, ecx
0x140077d36  mov     dword ptr [rsp+0A8h+var_78], ecx
0x140077d3a  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140077d41  mov     rcx, cs:VmsIfrLog
0x140077d48  mov     r9d, 2Eh ; '.'
0x140077d4e  mov     [rsp+0A8h+var_80], r15
0x140077d53  mov     dl, 2
0x140077d55  mov     [rsp+0A8h+var_88], rax
0x140077d5a  lea     r8d, [r9-1Ah]
0x140077d5e  call    WPP_RECORDER_SF_Zd
0x140077d63  jmp     loc_140077ECE
0x140077d68  lea     rax, [rbx+58h]
0x140077d6c  mov     word ptr [rbx+4Ah], 100h
0x140077d72  mov     [rbx+50h], rax
0x140077d76  lea     rcx, [rbx+48h]; DestinationString
0x140077d7a  xor     eax, eax
0x140077d7c  mov     rdx, r15; SourceString
0x140077d7f  mov     [rcx], ax
0x140077d82  xor     edi, edi
0x140077d84  call    cs:__imp_RtlCopyUnicodeString
0x140077d8b  nop     dword ptr [rax+rax+00h]
0x140077d90  lea     rax, [rbx+168h]
0x140077d97  mov     word ptr [rbx+15Ah], 100h
0x140077da0  mov     [rbx+160h], rax
0x140077da7  lea     rcx, [rbx+158h]; DestinationString
0x140077dae  xor     eax, eax
0x140077db0  mov     rdx, r13; SourceString
0x140077db3  mov     [rcx], ax
0x140077db6  call    cs:__imp_RtlCopyUnicodeString
0x140077dbd  nop     dword ptr [rax+rax+00h]
0x140077dc2  lea     rax, [rbx+278h]
0x140077dc9  mov     word ptr [rbx+26Ah], 200h
0x140077dd2  mov     [rbx+270h], rax
0x140077dd9  lea     rcx, [rbx+268h]; DestinationString
0x140077de0  xor     eax, eax
0x140077de2  mov     [rcx], ax
0x140077de5  test    r14, r14
0x140077de8  jz      short loc_140077DF9
0x140077dea  mov     rdx, r14; SourceString
0x140077ded  call    cs:__imp_RtlCopyUnicodeString
0x140077df4  nop     dword ptr [rax+rax+00h]
0x140077df9  lea     rcx, [rbx+20h]; SpinLock
0x140077dfd  mov     [rbx+40h], r12d
0x140077e01  mov     [rbx+44h], edi
0x140077e04  call    cs:__imp_KeInitializeSpinLock
0x140077e0b  nop     dword ptr [rax+rax+00h]
0x140077e10  mov     cl, [rsp+0A8h+arg_18]
0x140077e17  mov     dl, 2
0x140077e19  mov     dword ptr [rbx+28h], 1
0x140077e20  call    cs:__imp_NdisAllocateRefCount
0x140077e27  nop     dword ptr [rax+rax+00h]
0x140077e2c  mov     rcx, cs:VmsMiniportHandle; NdisHandle
0x140077e33  mov     [rbx+30h], rax
0x140077e37  mov     rax, [rsp+0A8h+arg_38]
0x140077e3f  mov     [rbx+4B8h], rax
0x140077e46  mov     [rbx+4C8h], edi
0x140077e4c  mov     byte ptr [rbx+4CCh], 1
0x140077e53  call    cs:__imp_NdisAllocateRWLock
0x140077e5a  nop     dword ptr [rax+rax+00h]
0x140077e5f  mov     [rbx+38h], rax
0x140077e63  test    rax, rax
0x140077e66  jnz     loc_140077EFD
0x140077e6c  mov     edi, 0C000009Ah
0x140077e71  mov     rcx, cs:VmsIfrLog
0x140077e78  lea     r9d, [rax+30h]
0x140077e7c  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140077e83  mov     dword ptr [rsp+0A8h+var_80], edi
0x140077e87  lea     r8d, [r9-1Ch]
0x140077e8b  mov     [rsp+0A8h+var_88], rax
0x140077e90  mov     dl, 2
0x140077e92  call    WPP_RECORDER_SF_d
0x140077e97  jmp     short loc_140077ECE
0x140077e99  mov     ecx, 0C0000033h
0x140077e9e  mov     edi, ecx
0x140077ea0  mov     dword ptr [rsp+0A8h+var_78], ecx
0x140077ea4  mov     r9d, 2Ch ; ','
0x140077eaa  mov     dword ptr [rsp+0A8h+var_80], edx
0x140077eae  mov     rcx, cs:VmsIfrLog
0x140077eb5  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140077ebc  mov     r8d, 14h
0x140077ec2  mov     [rsp+0A8h+var_88], rax
0x140077ec7  mov     dl, 2
0x140077ec9  call    WPP_RECORDER_SF_ld
0x140077ece  mov     rcx, rbx
0x140077ed1  call    VmsOmpObjectCleanup
0x140077ed6  mov     [rsp+0A8h+var_50], edi
0x140077eda  mov     [rsp+0A8h+var_58], r14
0x140077edf  mov     [rsp+0A8h+var_60], r13
0x140077ee4  mov     [rsp+0A8h+var_68], r15
0x140077ee9  mov     [rsp+0A8h+var_70], r12d
0x140077eee  mov     dword ptr [rsp+0A8h+var_78], ebp
0x140077ef2  mov     dword ptr [rsp+0A8h+var_80], esi
0x140077ef6  call    WPP_RECORDER_SF_DlLZZZd
0x140077efb  xor     ebx, ebx
0x140077efd  mov     rcx, [rsp+0A8h+arg_40]
0x140077f05  mov     eax, edi
0x140077f07  mov     [rcx], rbx
0x140077f0a  add     rsp, 68h
0x140077f0e  pop     r15
0x140077f10  pop     r14
0x140077f12  pop     r13
0x140077f14  pop     r12
0x140077f16  pop     rdi
0x140077f17  pop     rsi
0x140077f18  pop     rbp
0x140077f19  pop     rbx
0x140077f1a  retn
```
