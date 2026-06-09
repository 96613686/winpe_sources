# UTIL_WriteFile2(void *,void const *,ulong,_OVERLAPPED *)

- ea: `0x18001aa84`
- end: `0x18001aaf8`
- name: `?UTIL_WriteFile2@@YAJPEAXPEBXKPEAU_OVERLAPPED@@@Z`
- size: `116`
- prototype: `int(void *, const void *, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180018060`

## callees

- `0x18001aa84`

## import_xrefs

- `ntdll!NtWriteFile` at `0x18001aacf`
- `ntdll!NtWriteFile` at `0x18001aacf`
- `ntdll!RtlNtStatusToDosError` at `0x18001aaed`
- `ntdll!RtlNtStatusToDosError` at `0x18001aaed`

## pseudocode

```c
ULONG __fastcall UTIL_WriteFile2(void *a1, void *a2, ULONG a3, struct _IO_STATUS_BLOCK *a4)
{
  bool v4; // zf
  struct _OVERLAPPED *v6; // r9
  HANDLE Information; // rdx
  int v8; // eax
  union _LARGE_INTEGER v11; // [rsp+78h] [rbp+20h] BYREF

  v4 = (a4[1].Information & 1) == 0;
  a4->Pointer = (PVOID)259;
  v6 = 0;
  if ( v4 )
    v6 = (struct _OVERLAPPED *)a4;
  Information = (HANDLE)a4[1].Information;
  v11.QuadPart = 0;
  v8 = NtWriteFile(a1, Information, 0, v6, a4, a2, a3, &v11, 0);
  if ( v8 == 259 )
    return 997;
  if ( v8 < 0 )
    return RtlNtStatusToDosError(v8);
  return 0;
}

```

## disassembly

```asm
0x18001aa84  mov     r11, rsp
0x18001aa87  sub     rsp, 58h
0x18001aa8b  test    byte ptr [r9+18h], 1
0x18001aa90  lea     r10, [r11+20h]
0x18001aa94  mov     rax, r9
0x18001aa97  mov     qword ptr [r11-18h], 0
0x18001aa9f  mov     [r11-20h], r10
0x18001aaa3  mov     [r11-28h], r8d
0x18001aaa7  mov     qword ptr [r9], 103h
0x18001aaae  mov     r9d, 0
0x18001aab4  mov     [r11-30h], rdx
0x18001aab8  cmovz   r9, rax; ApcContext
0x18001aabc  mov     rdx, [rax+18h]; Event
0x18001aac0  xor     r8d, r8d; ApcRoutine
0x18001aac3  mov     qword ptr [r11+20h], 0
0x18001aacb  mov     [r11-38h], rax
0x18001aacf  call    cs:__imp_NtWriteFile
0x18001aad5  cmp     eax, 103h
0x18001aada  jnz     short loc_18001AAE3
0x18001aadc  mov     eax, 3E5h
0x18001aae1  jmp     short loc_18001AAF3
0x18001aae3  test    eax, eax
0x18001aae5  js      short loc_18001AAEB
0x18001aae7  xor     eax, eax
0x18001aae9  jmp     short loc_18001AAF3
0x18001aaeb  mov     ecx, eax; Status
0x18001aaed  call    cs:__imp_RtlNtStatusToDosError
0x18001aaf3  add     rsp, 58h
0x18001aaf7  retn
```
