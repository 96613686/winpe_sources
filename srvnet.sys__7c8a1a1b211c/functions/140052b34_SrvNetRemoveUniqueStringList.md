# SrvNetRemoveUniqueStringList

- ea: `0x140052b34`
- end: `0x140052c01`
- name: `SrvNetRemoveUniqueStringList`
- size: `205`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400079a0`
- `0x140008bb0`
- `0x1400527c0`

## callees

- `0x140007ec0`
- `0x140052b34`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140052bb8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140052bb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052b8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052b8c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140052b69`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140052b69`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140052b58`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140052b58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052b80`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052b80`

## pseudocode

```c
__int64 __fastcall SrvNetRemoveUniqueStringList(PCUNICODE_STRING String1, _QWORD *a2)
{
  struct _ERESOURCE *v2; // rbp
  unsigned int v5; // edi
  _QWORD *i; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rcx

  v2 = SrvNetDeviceExtension;
  v5 = -1073741772;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v2, 1u);
  for ( i = (_QWORD *)*a2; i != a2; i = (_QWORD *)*i )
  {
    if ( RtlEqualUnicodeString(String1, (PCUNICODE_STRING)(i + 3), 1u) )
    {
      if ( (*((_DWORD *)i + 4))-- == 1 )
      {
        v8 = (_QWORD *)*i;
        if ( *(_QWORD **)(*i + 8LL) != i || (v9 = (_QWORD *)i[1], (_QWORD *)*v9 != i) )
          __fastfail(3u);
        *v9 = v8;
        v8[1] = v9;
        SrvNetWskNotifyCleanupProviderContext(i);
      }
      v5 = 0;
      break;
    }
  }
  ExReleaseResourceLite(v2);
  KeLeaveCriticalRegion();
  return v5;
}

```

## disassembly

```asm
0x140052b34  mov     [rsp+arg_0], rbx
0x140052b39  mov     [rsp+arg_8], rbp
0x140052b3e  push    rsi
0x140052b3f  push    rdi
0x140052b40  push    r14
0x140052b42  sub     rsp, 20h
0x140052b46  mov     rbp, cs:SrvNetDeviceExtension
0x140052b4d  mov     rsi, rdx
0x140052b50  mov     r14, rcx
0x140052b53  mov     edi, 0C0000034h
0x140052b58  call    cs:__imp_KeEnterCriticalRegion
0x140052b5f  nop     dword ptr [rax+rax+00h]
0x140052b64  mov     dl, 1; Wait
0x140052b66  mov     rcx, rbp; Resource
0x140052b69  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140052b70  nop     dword ptr [rax+rax+00h]
0x140052b75  mov     rbx, [rsi]
0x140052b78  cmp     rbx, rsi
0x140052b7b  jnz     short loc_140052BAE
0x140052b7d  mov     rcx, rbp; Resource
0x140052b80  call    cs:__imp_ExReleaseResourceLite
0x140052b87  nop     dword ptr [rax+rax+00h]
0x140052b8c  call    cs:__imp_KeLeaveCriticalRegion
0x140052b93  nop     dword ptr [rax+rax+00h]
0x140052b98  mov     rbx, [rsp+38h+arg_0]
0x140052b9d  mov     eax, edi
0x140052b9f  mov     rbp, [rsp+38h+arg_8]
0x140052ba4  add     rsp, 20h
0x140052ba8  pop     r14
0x140052baa  pop     rdi
0x140052bab  pop     rsi
0x140052bac  retn
0x140052bae  lea     rdx, [rbx+18h]; String2
0x140052bb2  mov     r8b, 1; CaseInSensitive
0x140052bb5  mov     rcx, r14; String1
0x140052bb8  call    cs:__imp_RtlEqualUnicodeString
0x140052bbf  nop     dword ptr [rax+rax+00h]
0x140052bc4  test    al, al
0x140052bc6  jnz     short loc_140052BF2
0x140052bc8  mov     rbx, [rbx]
0x140052bcb  jmp     short loc_140052B78
0x140052bcd  mov     rax, [rbx]
0x140052bd0  cmp     [rax+8], rbx
0x140052bd4  jnz     short loc_140052BFA
0x140052bd6  mov     rcx, [rbx+8]
0x140052bda  cmp     [rcx], rbx
0x140052bdd  jnz     short loc_140052BFA
0x140052bdf  mov     [rcx], rax
0x140052be2  mov     [rax+8], rcx
0x140052be6  mov     rcx, rbx
0x140052be9  call    SrvNetWskNotifyCleanupProviderContext
0x140052bee  xor     edi, edi
0x140052bf0  jmp     short loc_140052B7D
0x140052bf2  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x140052bf6  jnz     short loc_140052BEE
0x140052bf8  jmp     short loc_140052BCD
0x140052bfa  mov     ecx, 3
0x140052bff  int     29h; Win8: RtlFailFast(ecx)
```
