# ScRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x14000bcc4`
- end: `0x14000beb4`
- name: `?ScRegOpenKeyExW@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z`
- size: `496`
- prototype: `ULONG __fastcall(HKEY, unsigned __int16 *, __int64, ACCESS_MASK, HKEY *KeyHandle)`
- caller_count: `40`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ac68`
- `0x14000bb80`
- `0x14000cb18`
- `0x14000d58c`
- `0x140010064`
- `0x14001064c`
- `0x140015ba4`
- `0x140015fd8`
- `0x140027074`
- `0x1400273fc`
- `0x1400282a4`
- `0x140028fb4`
- `0x14002b3ec`
- `0x14002cfec`
- `0x14002edf8`
- `0x14002f90c`
- `0x140034234`
- `0x140034b1c`
- `0x140037480`
- `0x140037614`
- `0x1400376c4`
- `0x140037830`
- `0x140039bd4`
- `0x14003fc10`
- `0x140041778`
- `0x140042b24`
- `0x140042d30`
- `0x140044448`
- `0x14006539c`
- `0x14006573c`
- `0x140065a14`
- `0x140065d60`
- `0x14006fe44`
- `0x140076194`
- `0x140076eb0`
- `0x140079d10`
- `0x14007a248`
- `0x14007abec`
- `0x14007ae5c`
- `0x1400848e0`

## callees

- `0x140004c58`
- `0x14000bcc4`
- `0x14000cee0`
- `0x14001a230`
- `0x14001f99c`
- `0x14007b7dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000bd5b`
- `ntdll!RtlNtStatusToDosError` at `0x14000bd5b`
- `ntdll!RtlInitUnicodeString` at `0x14000bd0a`
- `ntdll!RtlInitUnicodeString` at `0x14000bd0a`
- `ntdll!RtlFreeHeap` at `0x14000be31`
- `ntdll!RtlFreeHeap` at `0x14000bea9`
- `ntdll!RtlFreeHeap` at `0x14000be31`
- `ntdll!RtlFreeHeap` at `0x14000bea9`
- `ntdll!NtOpenKey` at `0x14000bd3d`
- `ntdll!NtOpenKey` at `0x14000be49`
- `ntdll!NtOpenKey` at `0x14000bd3d`
- `ntdll!NtOpenKey` at `0x14000be49`
- `ntdll!RtlAllocateHeap` at `0x14000bd9c`
- `ntdll!RtlAllocateHeap` at `0x14000bd9c`

## string_xrefs

- `0x14000bddd`: `\REGISTRY\MACHINE\`

## pseudocode

```c
ULONG __fastcall ScRegOpenKeyExW(HKEY a1, unsigned __int16 *a2, __int64 a3, ACCESS_MASK a4, HKEY *KeyHandle)
{
  HKEY v7; // r15
  unsigned __int16 *v8; // rdi
  int v9; // r14d
  int v10; // esi
  __int64 v12; // rax
  SIZE_T v13; // r15
  unsigned __int16 *Heap; // rax
  unsigned int v15; // esi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  v7 = a1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( a1 == HKEY_LOCAL_MACHINE )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = (unsigned int)(2 * v12 + 40);
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    v8 = Heap;
    if ( !Heap )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 111, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
      return 8;
    }
    v9 = 1;
    StringCbCopyW(Heap, v13, L"\\REGISTRY\\MACHINE\\");
    StringCbCatW(v8, v13, a2);
    v7 = 0;
  }
  else
  {
    v8 = a2;
    v9 = 0;
  }
  RtlInitUnicodeString(&DestinationString, v8);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  v10 = NtOpenKey((PHANDLE)KeyHandle, a4, &ObjectAttributes);
  if ( v10 != -1073741790 )
  {
LABEL_4:
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    return RtlNtStatusToDosError(v10);
  }
  v15 = ScTakeOwnership(&ObjectAttributes);
  if ( !v15 )
  {
    v10 = NtOpenKey((PHANDLE)KeyHandle, a4, &ObjectAttributes);
    if ( v10 < 0
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 112, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v10);
    }
    goto LABEL_4;
  }
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return v15;
}

```

## disassembly

```asm
0x14000bcc4  push    rbp
0x14000bcc6  push    rbx
0x14000bcc7  push    rsi
0x14000bcc8  push    rdi
0x14000bcc9  push    r12
0x14000bccb  push    r14
0x14000bccd  push    r15
0x14000bccf  mov     rbp, rsp
0x14000bcd2  sub     rsp, 60h
0x14000bcd6  xorps   xmm0, xmm0
0x14000bcd9  mov     r12d, r9d
0x14000bcdc  mov     rsi, rdx
0x14000bcdf  mov     r15, rcx
0x14000bce2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000bce6  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000bcea  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000bcee  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000bcf2  cmp     rcx, 0FFFFFFFF80000002h
0x14000bcf9  jz      short loc_14000BD70
0x14000bcfb  xor     ebx, ebx
0x14000bcfd  mov     rdi, rdx
0x14000bd00  mov     r14d, ebx
0x14000bd03  mov     rdx, rdi; SourceString
0x14000bd06  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000bd0a  call    cs:__imp_RtlInitUnicodeString
0x14000bd10  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000bd14  lea     rax, [rbp+DestinationString]
0x14000bd18  xorps   xmm0, xmm0
0x14000bd1b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000bd1f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000bd23  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000bd2a  mov     edx, r12d; DesiredAccess
0x14000bd2d  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x14000bd31  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000bd36  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14000bd3d  call    cs:__imp_NtOpenKey
0x14000bd43  mov     esi, eax
0x14000bd45  cmp     eax, 0C0000022h
0x14000bd4a  jz      loc_14000BE0B
0x14000bd50  test    r14d, r14d
0x14000bd53  jnz     loc_14000BE97
0x14000bd59  mov     ecx, esi; Status
0x14000bd5b  call    cs:__imp_RtlNtStatusToDosError
0x14000bd61  add     rsp, 60h
0x14000bd65  pop     r15
0x14000bd67  pop     r14
0x14000bd69  pop     r12
0x14000bd6b  pop     rdi
0x14000bd6c  pop     rsi
0x14000bd6d  pop     rbx
0x14000bd6e  pop     rbp
0x14000bd6f  retn
0x14000bd70  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bd74  xor     ebx, ebx
0x14000bd76  inc     rax
0x14000bd79  cmp     [rdx+rax*2], bx
0x14000bd7d  jnz     short loc_14000BD76
0x14000bd7f  mov     rcx, gs:60h
0x14000bd88  lea     rax, ds:28h[rax*2]
0x14000bd90  mov     r8d, eax; Size
0x14000bd93  xor     edx, edx; Flags
0x14000bd95  mov     r15d, eax
0x14000bd98  mov     rcx, [rcx+30h]; HeapHandle
0x14000bd9c  call    cs:__imp_RtlAllocateHeap
0x14000bda2  mov     rdi, rax
0x14000bda5  test    rax, rax
0x14000bda8  jnz     short loc_14000BDDD
0x14000bdaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdb1  lea     rax, WPP_GLOBAL_Control
0x14000bdb8  cmp     rcx, rax
0x14000bdbb  jz      short loc_14000BDD6
0x14000bdbd  test    byte ptr [rcx+1Ch], 1
0x14000bdc1  jz      short loc_14000BDD6
0x14000bdc3  mov     rcx, [rcx+10h]
0x14000bdc7  lea     edx, [rdi+6Fh]
0x14000bdca  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000bdd1  call    WPP_SF_
0x14000bdd6  mov     eax, 8
0x14000bddb  jmp     short loc_14000BD61
0x14000bddd  lea     r8, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\"
0x14000bde4  mov     rdx, r15; unsigned __int64
0x14000bde7  mov     rcx, rdi; unsigned __int16 *
0x14000bdea  mov     r14d, 1
0x14000bdf0  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14000bdf5  mov     r8, rsi; unsigned __int16 *
0x14000bdf8  mov     rdx, r15; unsigned __int64
0x14000bdfb  mov     rcx, rdi; unsigned __int16 *
0x14000bdfe  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000be03  mov     r15, rbx
0x14000be06  jmp     loc_14000BD03
0x14000be0b  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x14000be0f  call    ?ScTakeOwnership@@YAKPEAU_OBJECT_ATTRIBUTES@@@Z; ScTakeOwnership(_OBJECT_ATTRIBUTES *)
0x14000be14  mov     esi, eax
0x14000be16  test    eax, eax
0x14000be18  jz      short loc_14000BE3E
0x14000be1a  test    r14d, r14d
0x14000be1d  jz      short loc_14000BE37
0x14000be1f  mov     rcx, gs:60h
0x14000be28  mov     r8, rdi; P
0x14000be2b  xor     edx, edx; Flags
0x14000be2d  mov     rcx, [rcx+30h]; HeapHandle
0x14000be31  call    cs:__imp_RtlFreeHeap
0x14000be37  mov     eax, esi
0x14000be39  jmp     loc_14000BD61
0x14000be3e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000be42  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000be46  mov     edx, r12d; DesiredAccess
0x14000be49  call    cs:__imp_NtOpenKey
0x14000be4f  mov     esi, eax
0x14000be51  test    eax, eax
0x14000be53  jns     loc_14000BD50
0x14000be59  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be60  lea     rax, WPP_GLOBAL_Control
0x14000be67  cmp     rcx, rax
0x14000be6a  jz      loc_14000BD50
0x14000be70  test    byte ptr [rcx+1Ch], 1
0x14000be74  jz      loc_14000BD50
0x14000be7a  mov     rcx, [rcx+10h]
0x14000be7e  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000be85  mov     edx, 70h ; 'p'
0x14000be8a  mov     r9d, esi
0x14000be8d  call    WPP_SF_d
0x14000be92  jmp     loc_14000BD50
0x14000be97  mov     rcx, gs:60h
0x14000bea0  mov     r8, rdi; P
0x14000bea3  xor     edx, edx; Flags
0x14000bea5  mov     rcx, [rcx+30h]; HeapHandle
0x14000bea9  call    cs:__imp_RtlFreeHeap
0x14000beaf  jmp     loc_14000BD59
```
