# CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)

- ea: `0x14000bebc`
- end: `0x14000c10c`
- name: `?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(CServiceRecord *this, ACCESS_MASK, __int64, HKEY *)`
- caller_count: `28`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140009910`
- `0x14000b1f8`
- `0x14000b2e4`
- `0x14000bac8`
- `0x14000bb80`
- `0x14000cf60`
- `0x14000dc1c`
- `0x140014a8c`
- `0x140025ac4`
- `0x140028140`
- `0x140029908`
- `0x14002bf90`
- `0x140030258`
- `0x1400322dc`
- `0x14003ae4c`
- `0x14003c510`
- `0x1400406c8`
- `0x140062d1c`
- `0x140063144`
- `0x140068118`
- `0x140068b60`
- `0x14006b060`
- `0x14006e224`
- `0x1400706a0`
- `0x140071fe0`
- `0x140072cec`
- `0x14007b1cc`
- `0x140081f50`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000bebc`
- `0x14000cee0`
- `0x14001a230`
- `0x14001f99c`
- `0x14007b7dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000bf6b`
- `ntdll!RtlNtStatusToDosError` at `0x14000bf6b`
- `ntdll!RtlInitUnicodeString` at `0x14000bf14`
- `ntdll!RtlInitUnicodeString` at `0x14000bf14`
- `ntdll!RtlFreeHeap` at `0x14000c085`
- `ntdll!RtlFreeHeap` at `0x14000c101`
- `ntdll!RtlFreeHeap` at `0x14000c085`
- `ntdll!RtlFreeHeap` at `0x14000c101`
- `ntdll!NtOpenKey` at `0x14000bf46`
- `ntdll!NtOpenKey` at `0x14000c0a1`
- `ntdll!NtOpenKey` at `0x14000bf46`
- `ntdll!NtOpenKey` at `0x14000c0a1`
- `ntdll!RtlAllocateHeap` at `0x14000bfe6`
- `ntdll!RtlAllocateHeap` at `0x14000bfe6`

## string_xrefs

- `0x14000c031`: `\REGISTRY\MACHINE\`

## pseudocode

```c
__int64 __fastcall CServiceRecord::OpenServiceConfigKey(CServiceRecord *this, ACCESS_MASK a2, __int64 a3, HKEY *a4)
{
  __int64 v4; // rax
  const unsigned __int16 *v5; // r15
  void *v8; // rdi
  unsigned __int16 *v9; // rsi
  int v10; // r14d
  NTSTATUS v11; // edi
  ULONG v12; // edi
  PRPC_ASYNC_STATE v14; // rcx
  __int64 v15; // rax
  SIZE_T v16; // rdi
  unsigned __int16 *Heap; // rax
  NTSTATUS v18; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  v4 = *((_QWORD *)this + 27);
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 7);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v8 = *(void **)(v4 + 32);
  DestinationString = 0;
  if ( v8 == (void *)-2147483646LL )
  {
    v15 = -1;
    do
      ++v15;
    while ( v5[v15] );
    v16 = (unsigned int)(2 * v15 + 40);
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
    v9 = Heap;
    if ( !Heap )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 111, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      v12 = 8;
      goto LABEL_9;
    }
    v10 = 1;
    StringCbCopyW(Heap, v16, L"\\REGISTRY\\MACHINE\\");
    StringCbCatW(v9, v16, v5);
    v8 = 0;
  }
  else
  {
    v9 = (unsigned __int16 *)v5;
    v10 = 0;
  }
  RtlInitUnicodeString(&DestinationString, v9);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = v8;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenKey((PHANDLE)a4, a2, &ObjectAttributes);
  if ( v11 == -1073741790 )
  {
    v12 = ScTakeOwnership(&ObjectAttributes);
    if ( v12 )
    {
      if ( v10 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      goto LABEL_8;
    }
    v18 = NtOpenKey((PHANDLE)a4, a2, &ObjectAttributes);
    v11 = v18;
    if ( v18 < 0
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 112, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v18);
    }
  }
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  v12 = RtlNtStatusToDosError(v11);
  if ( v12 )
  {
LABEL_8:
    v14 = WPP_GLOBAL_Control;
LABEL_9:
    if ( v14 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v14->UserInfo) & 1) != 0 )
      WPP_SF_Sd(v14->StubInfo, 39, (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (_DWORD)v5, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x14000bebc  push    rbp
0x14000bebe  push    rbx
0x14000bebf  push    rsi
0x14000bec0  push    rdi
0x14000bec1  push    r12
0x14000bec3  push    r13
0x14000bec5  push    r14
0x14000bec7  push    r15
0x14000bec9  mov     rbp, rsp
0x14000becc  sub     rsp, 78h
0x14000bed0  mov     rax, [rcx+0D8h]
0x14000bed7  xorps   xmm0, xmm0
0x14000beda  mov     r15, [rcx+38h]
0x14000bede  mov     r12, r9
0x14000bee1  mov     r13d, edx
0x14000bee4  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000bee8  mov     rdi, [rax+20h]
0x14000beec  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000bef0  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000bef4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000bef8  cmp     rdi, 0FFFFFFFF80000002h
0x14000beff  jz      loc_14000BFBA
0x14000bf05  xor     ebx, ebx
0x14000bf07  mov     rsi, r15
0x14000bf0a  mov     r14d, ebx
0x14000bf0d  mov     rdx, rsi; SourceString
0x14000bf10  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000bf14  call    cs:__imp_RtlInitUnicodeString
0x14000bf1a  lea     rax, [rbp+DestinationString]
0x14000bf1e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000bf25  xorps   xmm0, xmm0
0x14000bf28  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000bf2c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000bf30  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x14000bf34  mov     edx, r13d; DesiredAccess
0x14000bf37  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14000bf3e  mov     rcx, r12; KeyHandle
0x14000bf41  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000bf46  call    cs:__imp_NtOpenKey
0x14000bf4c  mov     edi, eax
0x14000bf4e  cmp     eax, 0C0000022h
0x14000bf53  jz      loc_14000C05F
0x14000bf59  lea     r12, WPP_GLOBAL_Control
0x14000bf60  test    r14d, r14d
0x14000bf63  jnz     loc_14000C0EF
0x14000bf69  mov     ecx, edi; Status
0x14000bf6b  call    cs:__imp_RtlNtStatusToDosError
0x14000bf71  mov     edi, eax
0x14000bf73  test    eax, eax
0x14000bf75  jnz     short loc_14000BF8A
0x14000bf77  mov     eax, edi
0x14000bf79  add     rsp, 78h
0x14000bf7d  pop     r15
0x14000bf7f  pop     r14
0x14000bf81  pop     r13
0x14000bf83  pop     r12
0x14000bf85  pop     rdi
0x14000bf86  pop     rsi
0x14000bf87  pop     rbx
0x14000bf88  pop     rbp
0x14000bf89  retn
0x14000bf8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf91  cmp     rcx, r12
0x14000bf94  jz      short loc_14000BF77
0x14000bf96  test    byte ptr [rcx+1Ch], 1
0x14000bf9a  jz      short loc_14000BF77
0x14000bf9c  mov     rcx, [rcx+10h]
0x14000bfa0  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000bfa7  mov     edx, 27h ; '''
0x14000bfac  mov     [rsp+78h+var_58], edi
0x14000bfb0  mov     r9, r15
0x14000bfb3  call    WPP_SF_Sd
0x14000bfb8  jmp     short loc_14000BF77
0x14000bfba  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bfbe  xor     ebx, ebx
0x14000bfc0  inc     rax
0x14000bfc3  cmp     [r15+rax*2], bx
0x14000bfc8  jnz     short loc_14000BFC0
0x14000bfca  mov     rcx, gs:60h
0x14000bfd3  lea     rax, ds:28h[rax*2]
0x14000bfdb  mov     r8d, eax; Size
0x14000bfde  xor     edx, edx; Flags
0x14000bfe0  mov     edi, eax
0x14000bfe2  mov     rcx, [rcx+30h]; HeapHandle
0x14000bfe6  call    cs:__imp_RtlAllocateHeap
0x14000bfec  mov     rsi, rax
0x14000bfef  test    rax, rax
0x14000bff2  jnz     short loc_14000C031
0x14000bff4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bffb  lea     r12, WPP_GLOBAL_Control
0x14000c002  cmp     rcx, r12
0x14000c005  jz      short loc_14000C027
0x14000c007  test    byte ptr [rcx+1Ch], 1
0x14000c00b  jz      short loc_14000C027
0x14000c00d  mov     rcx, [rcx+10h]
0x14000c011  lea     edx, [rax+6Fh]
0x14000c014  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000c01b  call    WPP_SF_
0x14000c020  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c027  mov     edi, 8
0x14000c02c  jmp     loc_14000BF91
0x14000c031  lea     r8, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\"
0x14000c038  mov     rdx, rdi; unsigned __int64
0x14000c03b  mov     rcx, rsi; unsigned __int16 *
0x14000c03e  mov     r14d, 1
0x14000c044  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14000c049  mov     r8, r15; unsigned __int16 *
0x14000c04c  mov     rdx, rdi; unsigned __int64
0x14000c04f  mov     rcx, rsi; unsigned __int16 *
0x14000c052  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000c057  mov     rdi, rbx
0x14000c05a  jmp     loc_14000BF0D
0x14000c05f  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x14000c063  call    ?ScTakeOwnership@@YAKPEAU_OBJECT_ATTRIBUTES@@@Z; ScTakeOwnership(_OBJECT_ATTRIBUTES *)
0x14000c068  mov     edi, eax
0x14000c06a  test    eax, eax
0x14000c06c  jz      short loc_14000C097
0x14000c06e  test    r14d, r14d
0x14000c071  jz      short loc_14000C08B
0x14000c073  mov     rcx, gs:60h
0x14000c07c  mov     r8, rsi; P
0x14000c07f  xor     edx, edx; Flags
0x14000c081  mov     rcx, [rcx+30h]; HeapHandle
0x14000c085  call    cs:__imp_RtlFreeHeap
0x14000c08b  lea     r12, WPP_GLOBAL_Control
0x14000c092  jmp     loc_14000BF8A
0x14000c097  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000c09b  mov     edx, r13d; DesiredAccess
0x14000c09e  mov     rcx, r12; KeyHandle
0x14000c0a1  call    cs:__imp_NtOpenKey
0x14000c0a7  mov     edi, eax
0x14000c0a9  test    eax, eax
0x14000c0ab  jns     loc_14000BF59
0x14000c0b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c0b8  lea     r12, WPP_GLOBAL_Control
0x14000c0bf  cmp     rcx, r12
0x14000c0c2  jz      loc_14000BF60
0x14000c0c8  test    byte ptr [rcx+1Ch], 1
0x14000c0cc  jz      loc_14000BF60
0x14000c0d2  mov     rcx, [rcx+10h]
0x14000c0d6  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000c0dd  mov     edx, 70h ; 'p'
0x14000c0e2  mov     r9d, eax
0x14000c0e5  call    WPP_SF_d
0x14000c0ea  jmp     loc_14000BF60
0x14000c0ef  mov     rcx, gs:60h
0x14000c0f8  mov     r8, rsi; P
0x14000c0fb  xor     edx, edx; Flags
0x14000c0fd  mov     rcx, [rcx+30h]; HeapHandle
0x14000c101  call    cs:__imp_RtlFreeHeap
0x14000c107  jmp     loc_14000BF69
```
