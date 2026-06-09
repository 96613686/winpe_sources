# CGroupPolicy::CheckIfSecurityShouldBeSet(void *,_SP_DEVINFO_DATA *,uchar *,ulong)

- ea: `0x18000fb7c`
- end: `0x18000fc1c`
- name: `?CheckIfSecurityShouldBeSet@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@PEAEK@Z`
- size: `160`
- prototype: `__int64 __fastcall(CGroupPolicy *this, void *, struct _SP_DEVINFO_DATA *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eda4`

## callees

- `0x180002fa0`
- `0x18000fb7c`
- `0x18000ff88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc02`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000fbd8`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000fbd8`

## string_xrefs

- `0x18000fbe3`: `No change in security descriptor\n`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::CheckIfSecurityShouldBeSet(
        CGroupPolicy *this,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  unsigned int v5; // ebx
  __int64 v8; // rbx
  unsigned int v9; // ebx
  void *Source2; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Length; // [rsp+50h] [rbp+8h] BYREF
  int Length_4; // [rsp+54h] [rbp+Ch]

  Length_4 = HIDWORD(this);
  v5 = a5;
  Source2 = 0;
  Length = 0;
  if ( !a5 )
    return 1;
  if ( CGroupPolicy::GetDeviceSecurity(this, a2, a3, (unsigned __int8 **)&Source2, &Length) )
  {
    if ( Length == v5 && (v8 = Length, RtlCompareMemory(a4, Source2, Length) == v8) )
    {
      GPDebugPrintX(8u, "No change in security descriptor\n");
      v9 = 0;
    }
    else
    {
      v9 = 1;
    }
    LocalFree(Source2);
  }
  else
  {
    return 1;
  }
  return v9;
}

```

## disassembly

```asm
0x18000fb7c  mov     rax, rsp
0x18000fb7f  mov     [rax+10h], rbx
0x18000fb83  mov     [rax+8], rcx
0x18000fb87  push    rdi
0x18000fb88  sub     rsp, 40h
0x18000fb8c  mov     ebx, [rsp+48h+arg_20]
0x18000fb90  mov     rdi, r9
0x18000fb93  mov     qword ptr [rax-18h], 0
0x18000fb9b  mov     dword ptr [rax+8], 0
0x18000fba2  test    ebx, ebx
0x18000fba4  jnz     short loc_18000FBAB
0x18000fba6  lea     eax, [rbx+1]
0x18000fba9  jmp     short loc_18000FC11
0x18000fbab  lea     rax, [rsp+48h+Length]
0x18000fbb0  lea     r9, [rsp+48h+Source2]; unsigned __int8 **
0x18000fbb5  mov     [rsp+48h+var_28], rax; unsigned int *
0x18000fbba  call    ?GetDeviceSecurity@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@PEAPEAEPEAK@Z; CGroupPolicy::GetDeviceSecurity(void *,_SP_DEVINFO_DATA *,uchar * *,ulong *)
0x18000fbbf  test    eax, eax
0x18000fbc1  jz      short loc_18000FC0A
0x18000fbc3  cmp     dword ptr [rsp+48h+Length], ebx
0x18000fbc7  jnz     short loc_18000FBF8
0x18000fbc9  mov     ebx, dword ptr [rsp+48h+Length]
0x18000fbcd  mov     rcx, rdi; Source1
0x18000fbd0  mov     rdx, [rsp+48h+Source2]; Source2
0x18000fbd5  mov     r8d, ebx; Length
0x18000fbd8  call    cs:__imp_RtlCompareMemory
0x18000fbde  cmp     rax, rbx
0x18000fbe1  jnz     short loc_18000FBF8
0x18000fbe3  lea     rdx, aNoChangeInSecu; "No change in security descriptor\n"
0x18000fbea  mov     ecx, 8; unsigned int
0x18000fbef  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000fbf4  xor     ebx, ebx
0x18000fbf6  jmp     short loc_18000FBFD
0x18000fbf8  mov     ebx, 1
0x18000fbfd  mov     rcx, [rsp+48h+Source2]; hMem
0x18000fc02  call    cs:__imp_LocalFree
0x18000fc08  jmp     short loc_18000FC0F
0x18000fc0a  mov     ebx, 1
0x18000fc0f  mov     eax, ebx
0x18000fc11  mov     rbx, [rsp+48h+arg_8]
0x18000fc16  add     rsp, 40h
0x18000fc1a  pop     rdi
0x18000fc1b  retn
```
