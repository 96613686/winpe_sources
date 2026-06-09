# WcRemoveInMemoryTombstone

- ea: `0x14001ce88`
- end: `0x14001cfe9`
- name: `WcRemoveInMemoryTombstone`
- size: `353`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, struct _FILE_OBJECT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001c688`
- `0x140031940`
- `0x140033fe0`

## callees

- `0x140001500`
- `0x14001ce88`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001cf7a`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001cf7a`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001cf59`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001cf59`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14001cee7`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14001cee7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001cf3c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001cf3c`
- `ntoskrnl!KeSetEvent` at `0x14001cf8e`
- `ntoskrnl!KeSetEvent` at `0x14001cf8e`
- `ntoskrnl!RtlHashUnicodeString` at `0x14001cf0d`
- `ntoskrnl!RtlHashUnicodeString` at `0x14001cf0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cfa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cfa7`
- `FLTMGR!FltReleaseContext` at `0x14001cfbd`
- `FLTMGR!FltReleaseContext` at `0x14001cfd1`
- `FLTMGR!FltReleaseContext` at `0x14001cfbd`
- `FLTMGR!FltReleaseContext` at `0x14001cfd1`

## pseudocode

```c
__int64 __fastcall WcRemoveInMemoryTombstone(struct _FLT_INSTANCE *a1, __int64 a2, struct _FILE_OBJECT *a3)
{
  NTSTATUS v3; // edi
  char ContextFileObject; // al
  char *v6; // rbx
  UNICODE_STRING *v7; // rsi
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v8; // rsi
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v9; // rax
  PFLT_CONTEXT v11; // [rsp+30h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-30h] BYREF
  ULONG HashValue; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  Context = 0;
  v11 = 0;
  HashValue = 0;
  ContextFileObject = WcGetContextFileObject(a1, a3, &Context, &v11);
  v6 = (char *)v11;
  if ( ContextFileObject )
  {
    if ( v11 )
    {
      if ( *((_QWORD *)v11 + 32) )
      {
        v7 = (UNICODE_STRING *)(a2 + 88);
        v3 = RtlDowncaseUnicodeString(v7, v7, 0);
        if ( v3 >= 0 )
        {
          v3 = RtlHashUnicodeString(v7, 1u, 0, &HashValue);
          if ( v3 >= 0 )
          {
            v8 = 0;
            KeWaitForSingleObject(v6 + 232, Executive, 0, 0, 0);
            v9 = RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)v6 + 32), HashValue, 0);
            if ( v9 )
            {
              v8 = v9;
              RtlRemoveEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)v6 + 32), v9, 0);
            }
            KeSetEvent((PRKEVENT)(v6 + 232), 0, 0);
            if ( v8 )
              ExFreePoolWithTag(v8, 0x74684357u);
          }
        }
      }
    }
  }
  if ( Context )
    FltReleaseContext(Context);
  if ( v6 )
    FltReleaseContext(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001ce88  mov     r11, rsp
0x14001ce8b  push    rbx
0x14001ce8c  push    rbp
0x14001ce8d  push    rsi
0x14001ce8e  push    rdi
0x14001ce8f  sub     rsp, 48h
0x14001ce93  mov     rax, r8
0x14001ce96  lea     r9, [r11-38h]
0x14001ce9a  xor     edi, edi
0x14001ce9c  lea     r8, [r11-30h]
0x14001cea0  mov     rsi, rdx
0x14001cea3  mov     [r11-30h], rdi
0x14001cea7  mov     rdx, rax; FileObject
0x14001ceaa  mov     [r11-38h], rdi
0x14001ceae  mov     [r11+20h], edi
0x14001ceb2  call    WcGetContextFileObject
0x14001ceb7  mov     rbx, [rsp+68h+var_38]
0x14001cebc  test    al, al
0x14001cebe  jz      loc_14001CFB3
0x14001cec4  test    rbx, rbx
0x14001cec7  jz      loc_14001CFB3
0x14001cecd  cmp     [rbx+100h], rdi
0x14001ced4  jz      loc_14001CFB3
0x14001ceda  add     rsi, 58h ; 'X'
0x14001cede  xor     r8d, r8d; AllocateDestinationString
0x14001cee1  mov     rdx, rsi; SourceString
0x14001cee4  mov     rcx, rsi; DestinationString
0x14001cee7  call    cs:__imp_RtlDowncaseUnicodeString
0x14001ceee  nop     dword ptr [rax+rax+00h]
0x14001cef3  mov     edi, eax
0x14001cef5  test    eax, eax
0x14001cef7  js      loc_14001CFB3
0x14001cefd  lea     r9, [rsp+68h+HashValue]; HashValue
0x14001cf05  xor     r8d, r8d; HashAlgorithm
0x14001cf08  mov     dl, 1; CaseInSensitive
0x14001cf0a  mov     rcx, rsi; String
0x14001cf0d  call    cs:__imp_RtlHashUnicodeString
0x14001cf14  nop     dword ptr [rax+rax+00h]
0x14001cf19  mov     edi, eax
0x14001cf1b  test    eax, eax
0x14001cf1d  js      loc_14001CFB3
0x14001cf23  lea     rbp, [rbx+0E8h]
0x14001cf2a  xor     esi, esi
0x14001cf2c  mov     rcx, rbp; Object
0x14001cf2f  mov     [rsp+68h+Timeout], rsi; Timeout
0x14001cf34  xor     r9d, r9d; Alertable
0x14001cf37  xor     r8d, r8d; WaitMode
0x14001cf3a  xor     edx, edx; WaitReason
0x14001cf3c  call    cs:__imp_KeWaitForSingleObject
0x14001cf43  nop     dword ptr [rax+rax+00h]
0x14001cf48  mov     edx, [rsp+68h+HashValue]; Signature
0x14001cf4f  xor     r8d, r8d; Context
0x14001cf52  mov     rcx, [rbx+100h]; HashTable
0x14001cf59  call    cs:__imp_RtlLookupEntryHashTable
0x14001cf60  nop     dword ptr [rax+rax+00h]
0x14001cf65  test    rax, rax
0x14001cf68  jz      short loc_14001CF86
0x14001cf6a  mov     rcx, [rbx+100h]; HashTable
0x14001cf71  xor     r8d, r8d; Context
0x14001cf74  mov     rdx, rax; Entry
0x14001cf77  mov     rsi, rax
0x14001cf7a  call    cs:__imp_RtlRemoveEntryHashTable
0x14001cf81  nop     dword ptr [rax+rax+00h]
0x14001cf86  xor     r8d, r8d; Wait
0x14001cf89  xor     edx, edx; Increment
0x14001cf8b  mov     rcx, rbp; Event
0x14001cf8e  call    cs:__imp_KeSetEvent
0x14001cf95  nop     dword ptr [rax+rax+00h]
0x14001cf9a  test    rsi, rsi
0x14001cf9d  jz      short loc_14001CFB3
0x14001cf9f  mov     edx, 74684357h; Tag
0x14001cfa4  mov     rcx, rsi; P
0x14001cfa7  call    cs:__imp_ExFreePoolWithTag
0x14001cfae  nop     dword ptr [rax+rax+00h]
0x14001cfb3  mov     rcx, [rsp+68h+Context]; Context
0x14001cfb8  test    rcx, rcx
0x14001cfbb  jz      short loc_14001CFC9
0x14001cfbd  call    cs:__imp_FltReleaseContext
0x14001cfc4  nop     dword ptr [rax+rax+00h]
0x14001cfc9  test    rbx, rbx
0x14001cfcc  jz      short loc_14001CFDD
0x14001cfce  mov     rcx, rbx; Context
0x14001cfd1  call    cs:__imp_FltReleaseContext
0x14001cfd8  nop     dword ptr [rax+rax+00h]
0x14001cfdd  mov     eax, edi
0x14001cfdf  add     rsp, 48h
0x14001cfe3  pop     rdi
0x14001cfe4  pop     rsi
0x14001cfe5  pop     rbp
0x14001cfe6  pop     rbx
0x14001cfe7  retn
```
