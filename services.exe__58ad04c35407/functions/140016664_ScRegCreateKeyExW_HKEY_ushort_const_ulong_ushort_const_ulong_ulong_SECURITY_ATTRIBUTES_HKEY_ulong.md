# ScRegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x140016664`
- end: `0x1400167fd`
- name: `?ScRegCreateKeyExW@@YAKPEAUHKEY__@@PEBGK1KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `409`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, __int64, const unsigned __int16 *, ULONG CreateOptions, ACCESS_MASK DesiredAccess, struct _SECURITY_ATTRIBUTES *, HKEY *KeyHandle, unsigned int *Disposition)`
- caller_count: `8`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140015020`
- `0x140015ba4`
- `0x140016844`
- `0x140076b18`
- `0x140079d10`
- `0x14007aa54`
- `0x14007abec`
- `0x14007ae5c`

## callees

- `0x14000cee0`
- `0x140016664`
- `0x14001a230`
- `0x14001f99c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1400167c4`
- `ntdll!RtlNtStatusToDosError` at `0x1400167c4`
- `ntdll!RtlInitUnicodeString` at `0x14001674f`
- `ntdll!RtlInitUnicodeString` at `0x14001675b`
- `ntdll!RtlInitUnicodeString` at `0x14001674f`
- `ntdll!RtlInitUnicodeString` at `0x14001675b`
- `ntdll!RtlFreeHeap` at `0x1400167e4`
- `ntdll!RtlFreeHeap` at `0x1400167e4`
- `ntdll!NtCreateKey` at `0x1400167bc`
- `ntdll!NtCreateKey` at `0x1400167bc`
- `ntdll!RtlAllocateHeap` at `0x1400166d8`
- `ntdll!RtlAllocateHeap` at `0x1400166d8`

## string_xrefs

- `0x14001671f`: `\REGISTRY\MACHINE\`

## pseudocode

```c
__int64 __fastcall ScRegCreateKeyExW(
        HKEY a1,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        ULONG CreateOptions,
        ACCESS_MASK DesiredAccess,
        struct _SECURITY_ATTRIBUTES *a7,
        HKEY *KeyHandle,
        unsigned int *Disposition)
{
  const unsigned __int16 *v9; // rsi
  HKEY v10; // r14
  __int64 v11; // rax
  ULONG v12; // r14d
  SIZE_T v13; // r15
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v15; // rdi
  void *lpSecurityDescriptor; // rcx
  NTSTATUS v17; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-51h] BYREF
  struct _UNICODE_STRING Class; // [rsp+50h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-31h] BYREF

  v9 = a2;
  v10 = a1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  Class = 0;
  if ( a1 == HKEY_LOCAL_MACHINE )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v12 = 8;
    v13 = (unsigned int)(2 * v11 + 38);
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v13);
    v15 = Heap;
    if ( !Heap )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 110, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
      return v12;
    }
    StringCbCopyW(Heap, v13, L"\\REGISTRY\\MACHINE\\");
    StringCbCatW(v15, v13, v9);
    a2 = v15;
    v10 = 0;
  }
  else
  {
    v15 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&Class, 0);
  if ( a7 )
    lpSecurityDescriptor = a7->lpSecurityDescriptor;
  else
    lpSecurityDescriptor = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = lpSecurityDescriptor;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v10;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.SecurityQualityOfService = 0;
  v17 = NtCreateKey((PHANDLE)KeyHandle, DesiredAccess, &ObjectAttributes, 0, &Class, CreateOptions, Disposition);
  v12 = RtlNtStatusToDosError(v17);
  if ( v15 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  return v12;
}

```

## disassembly

```asm
0x140016664  push    rbp
0x140016666  push    rbx
0x140016667  push    rsi
0x140016668  push    rdi
0x140016669  push    r14
0x14001666b  push    r15
0x14001666d  lea     rbp, [rsp-7]
0x140016672  sub     rsp, 98h
0x140016679  xorps   xmm0, xmm0
0x14001667c  xorps   xmm1, xmm1
0x14001667f  mov     rsi, rdx
0x140016682  mov     r14, rcx
0x140016685  movups  xmmword ptr [rbp+2Fh+ObjectAttributes.Length], xmm0
0x140016689  movups  xmmword ptr [rbp+2Fh+ObjectAttributes.ObjectName], xmm0
0x14001668d  movups  xmmword ptr [rbp+2Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140016691  movups  xmmword ptr [rbp+2Fh+DestinationString.Length], xmm0
0x140016695  movups  xmmword ptr [rbp+2Fh+var_70.Length], xmm1
0x140016699  cmp     rcx, 0FFFFFFFF80000002h
0x1400166a0  jnz     loc_140016747
0x1400166a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400166aa  xor     ebx, ebx
0x1400166ac  inc     rax
0x1400166af  cmp     [rdx+rax*2], bx
0x1400166b3  jnz     short loc_1400166AC
0x1400166b5  mov     rcx, gs:60h
0x1400166be  lea     eax, ds:26h[rax*2]
0x1400166c5  mov     r14d, 8
0x1400166cb  mov     r8d, eax; Size
0x1400166ce  mov     edx, r14d; Flags
0x1400166d1  mov     r15d, eax
0x1400166d4  mov     rcx, [rcx+30h]; HeapHandle
0x1400166d8  call    cs:__imp_RtlAllocateHeap
0x1400166de  mov     rdi, rax
0x1400166e1  test    rax, rax
0x1400166e4  jnz     short loc_14001671F
0x1400166e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166ed  lea     rax, WPP_GLOBAL_Control
0x1400166f4  cmp     rcx, rax
0x1400166f7  jz      loc_1400167EA
0x1400166fd  test    byte ptr [rcx+1Ch], 1
0x140016701  jz      loc_1400167EA
0x140016707  mov     rcx, [rcx+10h]
0x14001670b  lea     edx, [rdi+6Eh]
0x14001670e  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140016715  call    WPP_SF_
0x14001671a  jmp     loc_1400167EA
0x14001671f  lea     r8, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\"
0x140016726  mov     rdx, r15; unsigned __int64
0x140016729  mov     rcx, rdi; unsigned __int16 *
0x14001672c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140016731  mov     r8, rsi; unsigned __int16 *
0x140016734  mov     rdx, r15; unsigned __int64
0x140016737  mov     rcx, rdi; unsigned __int16 *
0x14001673a  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14001673f  mov     rdx, rdi; SourceString
0x140016742  mov     r14, rbx
0x140016745  jmp     short loc_14001674B
0x140016747  xor     ebx, ebx
0x140016749  mov     edi, ebx
0x14001674b  lea     rcx, [rbp+2Fh+DestinationString]; DestinationString
0x14001674f  call    cs:__imp_RtlInitUnicodeString
0x140016755  xor     edx, edx; SourceString
0x140016757  lea     rcx, [rbp+2Fh+var_70]; DestinationString
0x14001675b  call    cs:__imp_RtlInitUnicodeString
0x140016761  mov     rax, [rbp+2Fh+arg_30]
0x140016765  test    rax, rax
0x140016768  jz      short loc_140016770
0x14001676a  mov     rcx, [rax+8]
0x14001676e  jmp     short loc_140016773
0x140016770  mov     rcx, rbx
0x140016773  mov     edx, [rbp+2Fh+DesiredAccess]; DesiredAccess
0x140016776  lea     rax, [rbp+2Fh+DestinationString]
0x14001677a  mov     [rbp+2Fh+ObjectAttributes.ObjectName], rax
0x14001677e  lea     r8, [rbp+2Fh+ObjectAttributes]; ObjectAttributes
0x140016782  mov     rax, [rbp+2Fh+arg_40]
0x140016786  xor     r9d, r9d; TitleIndex
0x140016789  mov     [rsp+0C0h+Disposition], rax; Disposition
0x14001678e  mov     eax, [rbp+2Fh+arg_20]
0x140016791  mov     [rsp+0C0h+CreateOptions], eax; CreateOptions
0x140016795  lea     rax, [rbp+2Fh+var_70]
0x140016799  mov     [rbp+2Fh+ObjectAttributes.SecurityDescriptor], rcx
0x14001679d  mov     rcx, [rbp+2Fh+KeyHandle]; KeyHandle
0x1400167a1  mov     [rsp+0C0h+Class], rax; Class
0x1400167a6  mov     [rbp+2Fh+ObjectAttributes.Length], 30h ; '0'
0x1400167ad  mov     [rbp+2Fh+ObjectAttributes.RootDirectory], r14
0x1400167b1  mov     [rbp+2Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1400167b8  mov     [rbp+2Fh+ObjectAttributes.SecurityQualityOfService], rbx
0x1400167bc  call    cs:__imp_NtCreateKey
0x1400167c2  mov     ecx, eax; Status
0x1400167c4  call    cs:__imp_RtlNtStatusToDosError
0x1400167ca  mov     r14d, eax
0x1400167cd  test    rdi, rdi
0x1400167d0  jz      short loc_1400167EA
0x1400167d2  mov     rcx, gs:60h
0x1400167db  mov     r8, rdi; P
0x1400167de  xor     edx, edx; Flags
0x1400167e0  mov     rcx, [rcx+30h]; HeapHandle
0x1400167e4  call    cs:__imp_RtlFreeHeap
0x1400167ea  mov     eax, r14d
0x1400167ed  add     rsp, 98h
0x1400167f4  pop     r15
0x1400167f6  pop     r14
0x1400167f8  pop     rdi
0x1400167f9  pop     rsi
0x1400167fa  pop     rbx
0x1400167fb  pop     rbp
0x1400167fc  retn
```
