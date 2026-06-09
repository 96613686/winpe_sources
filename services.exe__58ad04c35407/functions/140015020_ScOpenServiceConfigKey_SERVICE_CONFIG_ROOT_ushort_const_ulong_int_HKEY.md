# ScOpenServiceConfigKey(_SERVICE_CONFIG_ROOT *,ushort const *,ulong,int,HKEY__ * *)

- ea: `0x140015020`
- end: `0x14001530e`
- name: `?ScOpenServiceConfigKey@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEBGKHPEAPEAUHKEY__@@@Z`
- size: `750`
- prototype: `ULONG __fastcall(struct _SERVICE_CONFIG_ROOT *, unsigned __int16 *, ACCESS_MASK, const unsigned __int16 *, HKEY *KeyHandle)`
- caller_count: `5`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140014824`
- `0x140014dec`
- `0x140066ef4`
- `0x1400709e0`
- `0x1400795ac`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000cee0`
- `0x140015020`
- `0x140016664`
- `0x14001a230`
- `0x14001f99c`
- `0x14007b7dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1400150ea`
- `ntdll!RtlNtStatusToDosError` at `0x1400150ea`
- `ntdll!RtlInitUnicodeString` at `0x140015082`
- `ntdll!RtlInitUnicodeString` at `0x140015082`
- `ntdll!RtlFreeHeap` at `0x140015292`
- `ntdll!RtlFreeHeap` at `0x140015303`
- `ntdll!RtlFreeHeap` at `0x140015292`
- `ntdll!RtlFreeHeap` at `0x140015303`
- `ntdll!NtOpenKey` at `0x1400150c6`
- `ntdll!NtOpenKey` at `0x1400152aa`
- `ntdll!NtOpenKey` at `0x1400150c6`
- `ntdll!NtOpenKey` at `0x1400152aa`
- `ntdll!RtlAllocateHeap` at `0x1400151f0`
- `ntdll!RtlAllocateHeap` at `0x1400151f0`

## string_xrefs

- `0x14001523f`: `\REGISTRY\MACHINE\`

## pseudocode

```c
ULONG __fastcall ScOpenServiceConfigKey(
        struct _SERVICE_CONFIG_ROOT *a1,
        unsigned __int16 *a2,
        ACCESS_MASK a3,
        const unsigned __int16 *a4,
        HKEY *KeyHandle)
{
  HKEY v5; // rbx
  int v8; // edi
  unsigned __int16 *v9; // rbp
  void **v10; // r15
  unsigned int v11; // ebx
  ULONG result; // eax
  unsigned int v13; // edi
  unsigned int v14; // ebx
  PRPC_ASYNC_STATE v15; // rcx
  __int64 v16; // rax
  SIZE_T v18; // rbx
  unsigned __int16 *Heap; // rax
  NTSTATUS v20; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-58h] BYREF
  unsigned int v23; // [rsp+D8h] [rbp+20h] BYREF

  v5 = (HKEY)*((_QWORD *)a1 + 4);
  v23 = 0;
  if ( !(_DWORD)a4 )
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    if ( v5 == HKEY_LOCAL_MACHINE )
    {
      v16 = -1;
      while ( a2[++v16] != 0 )
        ;
      v18 = (unsigned int)(2 * v16 + 40);
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
      v9 = Heap;
      if ( !Heap )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->StubInfo, 111, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
          v15 = WPP_GLOBAL_Control;
        }
        LOBYTE(v11) = 8;
        v13 = 8;
        goto LABEL_14;
      }
      v8 = 1;
      StringCbCopyW(Heap, v18, L"\\REGISTRY\\MACHINE\\");
      StringCbCatW(v9, v18, a2);
      v5 = 0;
    }
    else
    {
      v8 = 0;
      v9 = a2;
    }
    RtlInitUnicodeString(&DestinationString, v9);
    v10 = (void **)KeyHandle;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v5;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtOpenKey((PHANDLE)KeyHandle, a3, &ObjectAttributes);
    if ( v11 == -1073741790 )
    {
      v11 = ScTakeOwnership(&ObjectAttributes);
      if ( v11 )
      {
        if ( v8 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
        v13 = v11;
LABEL_13:
        v15 = WPP_GLOBAL_Control;
LABEL_14:
        if ( v15 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v15->UserInfo) & 1) != 0 )
          WPP_SF_Sd(v15->StubInfo, 39, (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (_DWORD)a2, v11);
        return v13;
      }
      v20 = NtOpenKey(v10, a3, &ObjectAttributes);
      v11 = v20;
      if ( v20 < 0
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 112, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v20);
      }
    }
    if ( v8 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    result = RtlNtStatusToDosError(v11);
    LOBYTE(v11) = result;
    v13 = result;
    if ( !result )
      return result;
    goto LABEL_13;
  }
  result = ScRegCreateKeyExW(v5, a2, a3, a4, 0, a3, 0, KeyHandle, &v23);
  v14 = result;
  if ( result
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      40,
      (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
      (_DWORD)a2,
      result);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x140015020  mov     rax, rsp
0x140015023  push    rbx
0x140015024  push    rsi
0x140015025  push    r12
0x140015027  push    r14
0x140015029  push    r15
0x14001502b  sub     rsp, 90h
0x140015032  mov     rbx, [rcx+20h]
0x140015036  xor     r15d, r15d
0x140015039  mov     [rax+20h], r15d
0x14001503d  mov     r14d, r8d
0x140015040  mov     rsi, rdx
0x140015043  test    r9d, r9d
0x140015046  jnz     loc_14001511C
0x14001504c  mov     [rax+8], rbp
0x140015050  xorps   xmm0, xmm0
0x140015053  mov     [rax+10h], rdi
0x140015057  movups  xmmword ptr [rax-58h], xmm0
0x14001505b  movups  xmmword ptr [rax-48h], xmm0
0x14001505f  movups  xmmword ptr [rax-38h], xmm0
0x140015063  movups  xmmword ptr [rax-68h], xmm0
0x140015067  cmp     rbx, 0FFFFFFFF80000002h
0x14001506e  jz      loc_1400151C1
0x140015074  mov     edi, r15d
0x140015077  mov     rbp, rdx
0x14001507a  mov     rdx, rbp; SourceString
0x14001507d  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x140015082  call    cs:__imp_RtlInitUnicodeString
0x140015088  mov     r15, [rsp+0B8h+KeyHandle]
0x140015090  lea     rax, [rsp+0B8h+DestinationString]
0x140015095  xorps   xmm0, xmm0
0x140015098  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x14001509d  mov     rcx, r15; KeyHandle
0x1400150a0  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x1400150a8  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1400150ad  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rbx
0x1400150b2  mov     edx, r14d; DesiredAccess
0x1400150b5  mov     [rsp+0B8h+ObjectAttributes.Attributes], 40h ; '@'
0x1400150bd  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400150c6  call    cs:__imp_NtOpenKey
0x1400150cc  lea     r12, WPP_GLOBAL_Control
0x1400150d3  mov     ebx, eax
0x1400150d5  cmp     eax, 0C0000022h
0x1400150da  jz      loc_14001526C
0x1400150e0  test    edi, edi
0x1400150e2  jnz     loc_1400152F1
0x1400150e8  mov     ecx, ebx; Status
0x1400150ea  call    cs:__imp_RtlNtStatusToDosError
0x1400150f0  mov     ebx, eax
0x1400150f2  mov     edi, eax
0x1400150f4  test    eax, eax
0x1400150f6  jnz     loc_14001518C
0x1400150fc  mov     rbp, [rsp+0B8h+arg_0]
0x140015104  mov     rdi, [rsp+0B8h+arg_8]
0x14001510c  add     rsp, 90h
0x140015113  pop     r15
0x140015115  pop     r14
0x140015117  pop     r12
0x140015119  pop     rsi
0x14001511a  pop     rbx
0x14001511b  retn
0x14001511c  lea     rax, [rsp+0B8h+arg_18]
0x140015124  mov     rcx, rbx; HKEY
0x140015127  mov     [rsp+0B8h+var_78], rax; unsigned int *
0x14001512c  mov     rax, [rsp+0B8h+KeyHandle]
0x140015134  mov     [rsp+0B8h+var_80], rax; HKEY *
0x140015139  mov     [rsp+0B8h+var_88], r15; struct _SECURITY_ATTRIBUTES *
0x14001513e  mov     [rsp+0B8h+var_90], r14d; unsigned int
0x140015143  mov     [rsp+0B8h+var_98], r15d; unsigned int
0x140015148  call    ?ScRegCreateKeyExW@@YAKPEAUHKEY__@@PEBGK1KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ScRegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x14001514d  mov     ebx, eax
0x14001514f  test    eax, eax
0x140015151  jz      short loc_14001510C
0x140015153  mov     rcx, cs:WPP_GLOBAL_Control
0x14001515a  lea     r12, WPP_GLOBAL_Control
0x140015161  cmp     rcx, r12
0x140015164  jz      short loc_14001510C
0x140015166  test    byte ptr [rcx+1Ch], 1
0x14001516a  jz      short loc_14001510C
0x14001516c  mov     rcx, [rcx+10h]
0x140015170  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140015177  mov     edx, 28h ; '('
0x14001517c  mov     [rsp+0B8h+var_98], eax
0x140015180  mov     r9, rsi
0x140015183  call    WPP_SF_Sd
0x140015188  mov     eax, ebx
0x14001518a  jmp     short loc_14001510C
0x14001518c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015193  cmp     rcx, r12
0x140015196  jz      short loc_1400151BA
0x140015198  test    byte ptr [rcx+1Ch], 1
0x14001519c  jz      short loc_1400151BA
0x14001519e  mov     rcx, [rcx+10h]
0x1400151a2  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x1400151a9  mov     edx, 27h ; '''
0x1400151ae  mov     [rsp+0B8h+var_98], ebx
0x1400151b2  mov     r9, rsi
0x1400151b5  call    WPP_SF_Sd
0x1400151ba  mov     eax, edi
0x1400151bc  jmp     loc_1400150FC
0x1400151c1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400151c8  cmp     [rdx+rax*2+2], r15w
0x1400151ce  lea     rax, [rax+1]
0x1400151d2  jnz     short loc_1400151C8
0x1400151d4  mov     rcx, gs:60h
0x1400151dd  lea     rax, ds:28h[rax*2]
0x1400151e5  mov     r8d, eax; Size
0x1400151e8  xor     edx, edx; Flags
0x1400151ea  mov     ebx, eax
0x1400151ec  mov     rcx, [rcx+30h]; HeapHandle
0x1400151f0  call    cs:__imp_RtlAllocateHeap
0x1400151f6  mov     rbp, rax
0x1400151f9  test    rax, rax
0x1400151fc  jnz     short loc_14001523F
0x1400151fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140015205  lea     r12, WPP_GLOBAL_Control
0x14001520c  cmp     rcx, r12
0x14001520f  jz      short loc_140015233
0x140015211  test    byte ptr [rcx+1Ch], 1
0x140015215  jz      short loc_140015233
0x140015217  mov     rcx, [rcx+10h]
0x14001521b  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140015222  mov     edx, 6Fh ; 'o'
0x140015227  call    WPP_SF_
0x14001522c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015233  mov     ebx, 8
0x140015238  mov     edi, ebx
0x14001523a  jmp     loc_140015193
0x14001523f  lea     r8, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\"
0x140015246  mov     rdx, rbx; unsigned __int64
0x140015249  mov     rcx, rbp; unsigned __int16 *
0x14001524c  mov     edi, 1
0x140015251  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140015256  mov     r8, rsi; unsigned __int16 *
0x140015259  mov     rdx, rbx; unsigned __int64
0x14001525c  mov     rcx, rbp; unsigned __int16 *
0x14001525f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140015264  mov     rbx, r15
0x140015267  jmp     loc_14001507A
0x14001526c  lea     rcx, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x140015271  call    ?ScTakeOwnership@@YAKPEAU_OBJECT_ATTRIBUTES@@@Z; ScTakeOwnership(_OBJECT_ATTRIBUTES *)
0x140015276  mov     ebx, eax
0x140015278  test    eax, eax
0x14001527a  jz      short loc_14001529F
0x14001527c  test    edi, edi
0x14001527e  jz      short loc_140015298
0x140015280  mov     rcx, gs:60h
0x140015289  mov     r8, rbp; P
0x14001528c  xor     edx, edx; Flags
0x14001528e  mov     rcx, [rcx+30h]; HeapHandle
0x140015292  call    cs:__imp_RtlFreeHeap
0x140015298  mov     edi, ebx
0x14001529a  jmp     loc_14001518C
0x14001529f  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1400152a4  mov     edx, r14d; DesiredAccess
0x1400152a7  mov     rcx, r15; KeyHandle
0x1400152aa  call    cs:__imp_NtOpenKey
0x1400152b0  mov     ebx, eax
0x1400152b2  test    eax, eax
0x1400152b4  jns     loc_1400150E0
0x1400152ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400152c1  cmp     rcx, r12
0x1400152c4  jz      loc_1400150E0
0x1400152ca  test    byte ptr [rcx+1Ch], 1
0x1400152ce  jz      loc_1400150E0
0x1400152d4  mov     rcx, [rcx+10h]
0x1400152d8  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x1400152df  mov     edx, 70h ; 'p'
0x1400152e4  mov     r9d, eax
0x1400152e7  call    WPP_SF_d
0x1400152ec  jmp     loc_1400150E0
0x1400152f1  mov     rcx, gs:60h
0x1400152fa  mov     r8, rbp; P
0x1400152fd  xor     edx, edx; Flags
0x1400152ff  mov     rcx, [rcx+30h]; HeapHandle
0x140015303  call    cs:__imp_RtlFreeHeap
0x140015309  jmp     loc_1400150E8
```
