# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *,void *,_GUID const *)

- ea: `0x18001cbe0`
- end: `0x18001cd92`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEBU_GUID@@PEAX2@Z`
- size: `434`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800060d0`
- `0x180007000`
- `0x180011a90`

## callees

- `0x18001cbe0`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001ccc0`
- `ntdll!EtwEventActivityIdControl` at `0x18001cd03`
- `ntdll!EtwEventActivityIdControl` at `0x18001ccc0`
- `ntdll!EtwEventActivityIdControl` at `0x18001cd03`
- `ntdll!EtwEventWrite` at `0x18001ccdc`
- `ntdll!EtwEventWrite` at `0x18001ccdc`
- `ntdll!EtwEventEnabled` at `0x18001cc1d`
- `ntdll!EtwEventEnabled` at `0x18001cc1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ccac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ccac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd12`

## string_xrefs

- `0x18001cd4f`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const struct _GUID *a5)
{
  __int64 v6; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  bool v12; // zf
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  signed int v14; // eax
  signed int v15; // esi
  EventManager *v16; // rcx
  _QWORD v18[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 *v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h]
  __int64 *v21; // [rsp+40h] [rbp-30h]
  __int64 v22; // [rsp+48h] [rbp-28h]
  const struct _GUID *v23; // [rsp+50h] [rbp-20h]
  __int64 v24; // [rsp+58h] [rbp-18h]

  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, a2) )
    return 0;
  v10 = -1;
  if ( a3 )
  {
    v19 = (__int64 *)a3;
    v11 = -1;
    do
      v12 = a3[++v11] == 0;
    while ( !v12 );
    v20 = (unsigned int)(2 * v11 + 2);
  }
  else
  {
    v19 = &qword_1800439C0;
    v20 = 2;
  }
  if ( a4 )
  {
    v21 = (__int64 *)a4;
    do
      v12 = a4[++v10] == 0;
    while ( !v12 );
    v22 = (unsigned int)(2 * v10 + 2);
  }
  else
  {
    v21 = &qword_1800439C0;
    v22 = 2;
  }
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v23 = a5;
  v24 = 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EtwEventActivityIdControl(2, a5);
  v14 = EtwEventWrite(*(_QWORD *)this, a2, 3, &v19);
  v18[0] = 0;
  v18[1] = 0;
  v15 = v14;
  EtwEventActivityIdControl(2, v18);
  LeaveCriticalSection(v13);
  if ( !v15 )
    return 0;
  EventManager::LogIt(v16, L"EventWrite error", v15);
  if ( v15 > 0 )
    return (unsigned __int16)v15 | 0x80070000;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001cbe0  mov     [rsp-28h+arg_10], rbx
0x18001cbe5  push    rbp
0x18001cbe6  push    rsi
0x18001cbe7  push    rdi
0x18001cbe8  push    r14
0x18001cbea  push    r15
0x18001cbec  mov     rbp, rsp
0x18001cbef  sub     rsp, 70h
0x18001cbf3  mov     rax, cs:__security_cookie
0x18001cbfa  xor     rax, rsp
0x18001cbfd  mov     [rbp+var_10], rax
0x18001cc01  mov     r15, [rbp+arg_20]
0x18001cc05  mov     rsi, rcx
0x18001cc08  mov     rcx, [rcx]
0x18001cc0b  mov     rbx, r9
0x18001cc0e  mov     rdi, r8
0x18001cc11  mov     r14, rdx
0x18001cc14  test    rcx, rcx
0x18001cc17  jz      loc_18001CD45
0x18001cc1d  call    cs:__imp_EtwEventEnabled
0x18001cc24  nop     dword ptr [rax+rax+00h]
0x18001cc29  test    al, al
0x18001cc2b  jz      loc_18001CD22
0x18001cc31  lea     rdx, qword_1800439C0
0x18001cc38  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001cc3f  test    rdi, rdi
0x18001cc42  jz      loc_18001CD6E
0x18001cc48  mov     [rbp+var_40], rdi
0x18001cc4c  mov     rcx, rax
0x18001cc4f  nop
0x18001cc50  cmp     word ptr [rdi+rcx*2+2], 0
0x18001cc56  lea     rcx, [rcx+1]
0x18001cc5a  jnz     short loc_18001CC50
0x18001cc5c  lea     ecx, ds:2[rcx*2]
0x18001cc63  xor     edi, edi
0x18001cc65  mov     dword ptr [rbp+var_38], ecx
0x18001cc68  mov     dword ptr [rbp+var_38+4], edi
0x18001cc6b  test    rbx, rbx
0x18001cc6e  jz      loc_18001CD81
0x18001cc74  mov     [rbp+var_30], rbx
0x18001cc78  nop     dword ptr [rax+rax+00000000h]
0x18001cc80  cmp     word ptr [rbx+rax*2+2], 0
0x18001cc86  lea     rax, [rax+1]
0x18001cc8a  jnz     short loc_18001CC80
0x18001cc8c  lea     eax, ds:2[rax*2]
0x18001cc93  mov     dword ptr [rbp+var_28+4], edi
0x18001cc96  mov     dword ptr [rbp+var_28], eax
0x18001cc99  lea     rbx, [rsi+8]
0x18001cc9d  mov     [rbp+var_20], r15
0x18001cca1  mov     rcx, rbx; lpCriticalSection
0x18001cca4  mov     [rbp+var_18], 10h
0x18001ccac  call    cs:__imp_EnterCriticalSection
0x18001ccb3  nop     dword ptr [rax+rax+00h]
0x18001ccb8  mov     rdx, r15
0x18001ccbb  mov     ecx, 2
0x18001ccc0  call    cs:__imp_EtwEventActivityIdControl
0x18001ccc7  nop     dword ptr [rax+rax+00h]
0x18001cccc  mov     rcx, [rsi]
0x18001cccf  lea     r9, [rbp+var_40]
0x18001ccd3  mov     r8d, 3
0x18001ccd9  mov     rdx, r14
0x18001ccdc  call    cs:__imp_EtwEventWrite
0x18001cce3  nop     dword ptr [rax+rax+00h]
0x18001cce8  lea     rdx, [rbp+var_50]
0x18001ccec  mov     [rbp+var_50], 0
0x18001ccf4  mov     ecx, 2
0x18001ccf9  mov     [rbp+var_48], 0
0x18001cd01  mov     esi, eax
0x18001cd03  call    cs:__imp_EtwEventActivityIdControl
0x18001cd0a  nop     dword ptr [rax+rax+00h]
0x18001cd0f  mov     rcx, rbx; lpCriticalSection
0x18001cd12  call    cs:__imp_LeaveCriticalSection
0x18001cd19  nop     dword ptr [rax+rax+00h]
0x18001cd1e  test    esi, esi
0x18001cd20  jnz     short loc_18001CD4C
0x18001cd22  xor     eax, eax
0x18001cd24  mov     rcx, [rbp+var_10]
0x18001cd28  xor     rcx, rsp; StackCookie
0x18001cd2b  call    __security_check_cookie
0x18001cd30  mov     rbx, [rsp+70h+arg_10]
0x18001cd38  add     rsp, 70h
0x18001cd3c  pop     r15
0x18001cd3e  pop     r14
0x18001cd40  pop     rdi
0x18001cd41  pop     rsi
0x18001cd42  pop     rbp
0x18001cd43  retn
0x18001cd45  mov     eax, 1
0x18001cd4a  jmp     short loc_18001CD24
0x18001cd4c  mov     r8d, esi; unsigned int
0x18001cd4f  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001cd56  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001cd5b  test    esi, esi
0x18001cd5d  jg      short loc_18001CD63
0x18001cd5f  mov     eax, esi
0x18001cd61  jmp     short loc_18001CD24
0x18001cd63  movzx   esi, si
0x18001cd66  or      esi, 80070000h
0x18001cd6c  jmp     short loc_18001CD5F
0x18001cd6e  mov     [rbp+var_40], rdx
0x18001cd72  xor     edi, edi
0x18001cd74  mov     [rbp+var_38], 2
0x18001cd7c  jmp     loc_18001CC6B
0x18001cd81  mov     [rbp+var_30], rdx
0x18001cd85  mov     [rbp+var_28], 2
0x18001cd8d  jmp     loc_18001CC99
```
