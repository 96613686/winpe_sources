# ScCreateUserSecurityObject

- ea: `0x140016220`
- end: `0x140016310`
- name: `ScCreateUserSecurityObject`
- size: `240`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR ParentDescriptor@<rcx>, PSECURITY_DESCRIPTOR CreatorDescriptor, BOOLEAN IsDirectoryObject, char, PGENERIC_MAPPING, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015df0`
- `0x140033b5c`

## callees

- `0x140016220`
- `0x140016318`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x140016292`
- `ntdll!NtOpenProcessToken` at `0x140016292`
- `ntdll!NtOpenThreadToken` at `0x140016308`
- `ntdll!NtOpenThreadToken` at `0x140016308`
- `ntdll!NtClose` at `0x1400162d4`
- `ntdll!NtClose` at `0x1400162d4`
- `ntdll!RtlFreeHeap` at `0x1400162e4`
- `ntdll!RtlFreeHeap` at `0x1400162e4`
- `ntdll!RtlNewSecurityObject` at `0x1400162c7`
- `ntdll!RtlNewSecurityObject` at `0x1400162c7`

## pseudocode

```c
__int64 __fastcall ScCreateUserSecurityObject(
        PSECURITY_DESCRIPTOR ParentDescriptor,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        PSECURITY_DESCRIPTOR CreatorDescriptor,
        BOOLEAN IsDirectoryObject,
        char a7,
        PGENERIC_MAPPING GenericMapping,
        PSECURITY_DESCRIPTOR *NewDescriptor)
{
  PVOID ProcessHeap; // rdi
  __int64 result; // rax
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CreatorDescriptor = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  result = ScCreateAndSetSD(a2, a3, LocalSystemSid, LocalSystemSid, (struct _ACL **)&CreatorDescriptor);
  if ( (int)result >= 0 )
  {
    if ( a7 )
      v12 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
    else
      v12 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v13 = RtlNewSecurityObject(
              ParentDescriptor,
              CreatorDescriptor,
              NewDescriptor,
              IsDirectoryObject,
              TokenHandle,
              GenericMapping);
      NtClose(TokenHandle);
    }
    RtlFreeHeap(ProcessHeap, 0, CreatorDescriptor);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x140016220  mov     rax, rsp
0x140016223  mov     [rax+8], rbx
0x140016227  mov     [rax+10h], rsi
0x14001622b  mov     [rax+20h], r9
0x14001622f  push    rdi
0x140016230  sub     rsp, 30h
0x140016234  mov     qword ptr [rax+20h], 0
0x14001623c  mov     r10d, r8d
0x14001623f  mov     r8, cs:LocalSystemSid
0x140016246  mov     r11, rdx
0x140016249  mov     qword ptr [rax+28h], 0
0x140016251  mov     rsi, rcx
0x140016254  mov     rax, gs:60h
0x14001625d  mov     r9, r8
0x140016260  mov     edx, r10d
0x140016263  mov     rcx, r11
0x140016266  mov     rdi, [rax+30h]
0x14001626a  lea     rax, [rsp+38h+CreatorDescriptor]
0x14001626f  mov     [rsp+38h+Token], rax
0x140016274  call    ScCreateAndSetSD
0x140016279  test    eax, eax
0x14001627b  js      short loc_1400162EC
0x14001627d  cmp     [rsp+38h+arg_30], 0
0x140016282  mov     edx, 8; DesiredAccess
0x140016287  jnz     short loc_1400162FC
0x140016289  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x14001628e  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140016292  call    cs:__imp_NtOpenProcessToken
0x140016298  mov     ebx, eax
0x14001629a  test    eax, eax
0x14001629c  js      short loc_1400162DA
0x14001629e  mov     rax, [rsp+38h+arg_38]
0x1400162a3  mov     rcx, rsi; ParentDescriptor
0x1400162a6  mov     r9b, [rsp+38h+IsDirectoryObject]; IsDirectoryObject
0x1400162ab  mov     r8, [rsp+38h+NewDescriptor]; NewDescriptor
0x1400162b3  mov     rdx, [rsp+38h+CreatorDescriptor]; CreatorDescriptor
0x1400162b8  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x1400162bd  mov     rax, [rsp+38h+TokenHandle]
0x1400162c2  mov     [rsp+38h+Token], rax; Token
0x1400162c7  call    cs:__imp_RtlNewSecurityObject
0x1400162cd  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x1400162d2  mov     ebx, eax
0x1400162d4  call    cs:__imp_NtClose
0x1400162da  mov     r8, [rsp+38h+CreatorDescriptor]; P
0x1400162df  xor     edx, edx; Flags
0x1400162e1  mov     rcx, rdi; HeapHandle
0x1400162e4  call    cs:__imp_RtlFreeHeap
0x1400162ea  mov     eax, ebx
0x1400162ec  mov     rbx, [rsp+38h+arg_0]
0x1400162f1  mov     rsi, [rsp+38h+arg_8]
0x1400162f6  add     rsp, 30h
0x1400162fa  pop     rdi
0x1400162fb  retn
0x1400162fc  xor     r8d, r8d; OpenAsSelf
0x1400162ff  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x140016304  lea     rcx, [r8-2]; ThreadHandle
0x140016308  call    cs:__imp_NtOpenThreadToken
0x14001630e  jmp     short loc_140016298
```
