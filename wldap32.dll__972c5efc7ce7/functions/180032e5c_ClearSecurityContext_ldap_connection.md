# ClearSecurityContext(ldap_connection *)

- ea: `0x180032e5c`
- end: `0x180032ede`
- name: `?ClearSecurityContext@@YAXPEAUldap_connection@@@Z`
- size: `130`
- prototype: `void __fastcall(struct ldap_connection *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017854`

## callees

- `0x180032e5c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032ed2`

## pseudocode

```c
void __fastcall ClearSecurityContext(struct ldap_connection *a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 512);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 512));
  if ( *(_OWORD *)((char *)a1 + 216) != __PAIR128__(-1, -1) )
  {
    ((void (__fastcall *)(char *))SspiFunctionTableW->DeleteSecurityContext)((char *)a1 + 216);
    *((_QWORD *)a1 + 27) = -1;
    *((_QWORD *)a1 + 28) = -1;
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180032e5c  mov     [rsp+arg_0], rbx
0x180032e61  mov     [rsp+arg_8], rsi
0x180032e66  push    rdi
0x180032e67  sub     rsp, 20h
0x180032e6b  lea     rdi, [rcx+200h]
0x180032e72  mov     rbx, rcx
0x180032e75  mov     rcx, rdi; lpCriticalSection
0x180032e78  call    cs:__imp_EnterCriticalSection
0x180032e7f  nop     dword ptr [rax+rax+00h]
0x180032e84  lea     rsi, [rbx+0D8h]
0x180032e8b  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180032e8f  jnz     short loc_180032E9B
0x180032e91  cmp     qword ptr [rbx+0E0h], 0FFFFFFFFFFFFFFFFh
0x180032e99  jz      short loc_180032EC0
0x180032e9b  mov     rax, cs:SspiFunctionTableW
0x180032ea2  mov     rcx, rsi
0x180032ea5  mov     rax, [rax+48h]
0x180032ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032eae  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180032eb5  mov     qword ptr [rbx+0E0h], 0FFFFFFFFFFFFFFFFh
0x180032ec0  mov     rcx, rdi
0x180032ec3  mov     rbx, [rsp+28h+arg_0]
0x180032ec8  mov     rsi, [rsp+28h+arg_8]
0x180032ecd  add     rsp, 20h
0x180032ed1  pop     rdi
0x180032ed2  jmp     cs:__imp_LeaveCriticalSection
```
