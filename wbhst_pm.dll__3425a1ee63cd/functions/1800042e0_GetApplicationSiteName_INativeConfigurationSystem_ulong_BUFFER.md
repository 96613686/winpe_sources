# GetApplicationSiteName(INativeConfigurationSystem *,ulong,BUFFER *)

- ea: `0x1800042e0`
- end: `0x1800043bf`
- name: `?GetApplicationSiteName@@YAJPEAVINativeConfigurationSystem@@KPEAVBUFFER@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct INativeConfigurationSystem *, unsigned int, struct BUFFER *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800038f0`
- `0x1800043c8`
- `0x1800045fc`

## callees

- `0x1800042e0`
- `0x180005010`

## import_xrefs

- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000435d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000435d`

## pseudocode

```c
__int64 __fastcall GetApplicationSiteName(struct INativeConfigurationSystem *a1, unsigned int a2, struct BUFFER *a3)
{
  __int64 result; // rax
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v8; // r8
  int v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v9 = 0;
  result = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64 *))(*(_QWORD *)a1 + 56LL))(a1, &v10);
  if ( (int)result >= 0 )
  {
    v6 = *((_QWORD *)a3 + 4);
    v9 = *((_DWORD *)a3 + 10) >> 1;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *, _QWORD))(*(_QWORD *)v10 + 24LL))(
           v10,
           a2,
           v6,
           &v9,
           0);
    if ( v7 == -2147024774 )
    {
      if ( !BUFFER::Resize(a3, 2 * v9) )
        return v7 - 108;
      v8 = *((_QWORD *)a3 + 4);
      v9 = *((_DWORD *)a3 + 10) >> 1;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *, _QWORD))(*(_QWORD *)v10 + 24LL))(
             v10,
             a2,
             v8,
             &v9,
             0);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800042e0  mov     rax, rsp
0x1800042e3  mov     [rax+10h], rbx
0x1800042e7  mov     [rax+18h], rsi
0x1800042eb  push    rdi
0x1800042ec  sub     rsp, 30h
0x1800042f0  mov     qword ptr [rax+20h], 0
0x1800042f8  mov     esi, edx
0x1800042fa  mov     dword ptr [rax+8], 0
0x180004301  lea     rdx, [rsp+38h+arg_18]
0x180004306  mov     rax, [rcx]
0x180004309  mov     rbx, r8
0x18000430c  mov     rax, [rax+38h]
0x180004310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004315  test    eax, eax
0x180004317  js      loc_1800043AF
0x18000431d  mov     eax, [rbx+28h]
0x180004320  lea     r9, [rsp+38h+arg_0]
0x180004325  mov     rcx, [rsp+38h+arg_18]
0x18000432a  mov     edx, esi
0x18000432c  mov     r8, [rbx+20h]
0x180004330  shr     eax, 1
0x180004332  mov     [rsp+38h+arg_0], eax
0x180004336  mov     rax, [rcx]
0x180004339  mov     [rsp+38h+var_18], 0
0x180004342  mov     rax, [rax+18h]
0x180004346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000434b  mov     edi, eax
0x18000434d  cmp     eax, 8007007Ah
0x180004352  jnz     short loc_18000439C
0x180004354  mov     edx, [rsp+38h+arg_0]
0x180004358  mov     rcx, rbx
0x18000435b  add     edx, edx
0x18000435d  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180004363  test    al, al
0x180004365  jnz     short loc_18000436C
0x180004367  lea     eax, [rdi-6Ch]
0x18000436a  jmp     short loc_1800043AF
0x18000436c  mov     eax, [rbx+28h]
0x18000436f  lea     r9, [rsp+38h+arg_0]
0x180004374  mov     rcx, [rsp+38h+arg_18]
0x180004379  mov     edx, esi
0x18000437b  mov     r8, [rbx+20h]
0x18000437f  shr     eax, 1
0x180004381  mov     [rsp+38h+arg_0], eax
0x180004385  mov     rax, [rcx]
0x180004388  mov     [rsp+38h+var_18], 0
0x180004391  mov     rax, [rax+18h]
0x180004395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000439a  mov     edi, eax
0x18000439c  mov     rcx, [rsp+38h+arg_18]
0x1800043a1  mov     rax, [rcx]
0x1800043a4  mov     rax, [rax+10h]
0x1800043a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ad  mov     eax, edi
0x1800043af  mov     rbx, [rsp+38h+arg_8]
0x1800043b4  mov     rsi, [rsp+38h+arg_10]
0x1800043b9  add     rsp, 30h
0x1800043bd  pop     rdi
0x1800043be  retn
```
