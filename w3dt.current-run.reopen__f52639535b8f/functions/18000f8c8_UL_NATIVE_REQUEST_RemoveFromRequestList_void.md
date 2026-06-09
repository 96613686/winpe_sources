# UL_NATIVE_REQUEST::RemoveFromRequestList(void)

- ea: `0x18000f8c8`
- end: `0x18000f927`
- name: `?RemoveFromRequestList@UL_NATIVE_REQUEST@@QEAAXXZ`
- size: `95`
- prototype: `void __fastcall(UL_NATIVE_REQUEST *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f770`
- `0x18000f7f0`

## callees

- `0x18000f8c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f8e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f8e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f919`

## pseudocode

```c
void __fastcall UL_NATIVE_REQUEST::RemoveFromRequestList(UL_NATIVE_REQUEST *this)
{
  UL_NATIVE_REQUEST **v2; // r8
  UL_NATIVE_REQUEST **v3; // rdx

  if ( UL_NATIVE_REQUEST::sm_fEnableRequestListDebugging )
  {
    EnterCriticalSection(&UL_NATIVE_REQUEST::sm_csRequestList);
    v2 = (UL_NATIVE_REQUEST **)*((_QWORD *)this + 379);
    if ( v2[1] != (UL_NATIVE_REQUEST *)((char *)this + 3032)
      || (v3 = (UL_NATIVE_REQUEST **)*((_QWORD *)this + 380), *v3 != (UL_NATIVE_REQUEST *)((char *)this + 3032)) )
    {
      __fastfail(3u);
    }
    *v3 = (UL_NATIVE_REQUEST *)v2;
    v2[1] = (UL_NATIVE_REQUEST *)v3;
    LeaveCriticalSection(&UL_NATIVE_REQUEST::sm_csRequestList);
  }
}

```

## disassembly

```asm
0x18000f8c8  push    rbx
0x18000f8ca  sub     rsp, 20h
0x18000f8ce  cmp     cs:?sm_fEnableRequestListDebugging@UL_NATIVE_REQUEST@@0HA, 0; int UL_NATIVE_REQUEST::sm_fEnableRequestListDebugging
0x18000f8d5  mov     rbx, rcx
0x18000f8d8  jnz     short loc_18000F8E0
0x18000f8da  add     rsp, 20h
0x18000f8de  pop     rbx
0x18000f8df  retn
0x18000f8e0  lea     rcx, ?sm_csRequestList@UL_NATIVE_REQUEST@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000f8e7  call    cs:__imp_EnterCriticalSection
0x18000f8ed  lea     rax, [rbx+0BD8h]
0x18000f8f4  mov     r8, [rax]
0x18000f8f7  cmp     [r8+8], rax
0x18000f8fb  jnz     short loc_18000F920
0x18000f8fd  mov     rdx, [rax+8]
0x18000f901  cmp     [rdx], rax
0x18000f904  jnz     short loc_18000F920
0x18000f906  mov     [rdx], r8
0x18000f909  lea     rcx, ?sm_csRequestList@UL_NATIVE_REQUEST@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION UL_NATIVE_REQUEST::sm_csRequestList
0x18000f910  mov     [r8+8], rdx
0x18000f914  add     rsp, 20h
0x18000f918  pop     rbx
0x18000f919  jmp     cs:__imp_LeaveCriticalSection
0x18000f920  mov     ecx, 3
0x18000f925  int     29h; Win8: RtlFailFast(ecx)
```
