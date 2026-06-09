# Worker::GetThreadTimes(CThreadTimes *)

- ea: `0x10048dee0`
- end: `0x10048dfa0`
- name: `?GetThreadTimes@Worker@@QEAAXPEAVCThreadTimes@@@Z`
- size: `192`
- prototype: `void __fastcall(Worker *__hidden this, struct CThreadTimes *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10058b8c0`

## callees

- `0x10048dee0`

## import_xrefs

- `KERNEL32!GetThreadTimes` at `0x10048df26`
- `KERNEL32!GetThreadTimes` at `0x10048df26`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048df36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048df5a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048df7e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048df36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048df5a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048df7e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048df42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048df66`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048df8a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048df42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048df66`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048df8a`

## pseudocode

```c
void __fastcall Worker::GetThreadTimes(Worker *this, struct _FILETIME *a2)
{
  __int64 v2; // rcx
  struct _FILETIME v3; // rax
  void *v5; // rcx
  __int64 v6; // rcx
  struct _FILETIME *v7; // rbx
  struct _FILETIME v8; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME v9; // [rsp+48h] [rbp+10h] BYREF
  struct _FILETIME v10; // [rsp+50h] [rbp+18h] BYREF
  struct _FILETIME v11; // [rsp+58h] [rbp+20h] BYREF

  v2 = *((_QWORD *)this + 78);
  v3 = 0;
  v10 = 0;
  v8 = 0;
  v9 = 0;
  if ( v2 )
  {
    v5 = *(void **)(v2 + 296);
    if ( v5 )
    {
      GetThreadTimes(v5, &v10, &v11, &v8, &v9);
      v3 = v8;
    }
  }
  if ( !a2 )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    v6 = 8;
LABEL_6:
    *(struct _FILETIME *)v6 = v9;
    goto LABEL_7;
  }
  v6 = (__int64)&a2[1];
  *a2 = v3;
  if ( a2 != (struct _FILETIME *)-8LL )
    goto LABEL_6;
  *_errno() = 22;
  _invalid_parameter_noinfo();
LABEL_7:
  v7 = a2 + 2;
  if ( v7 )
  {
    *v7 = v10;
  }
  else
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
}

```

## disassembly

```asm
0x10048dee0  mov     r11, rsp
0x10048dee3  push    rbx
0x10048dee4  sub     rsp, 30h
0x10048dee8  mov     rcx, [rcx+270h]
0x10048deef  xor     eax, eax
0x10048def1  mov     [r11+18h], rax
0x10048def5  mov     rbx, rdx
0x10048def8  mov     [rsp+38h+arg_0], rax
0x10048defd  mov     [r11+10h], rax
0x10048df01  test    rcx, rcx
0x10048df04  jz      short loc_10048DF31
0x10048df06  mov     rcx, [rcx+128h]; hThread
0x10048df0d  test    rcx, rcx
0x10048df10  jz      short loc_10048DF31
0x10048df12  lea     rax, [r11+10h]
0x10048df16  lea     r9, [r11+8]; lpKernelTime
0x10048df1a  mov     [r11-18h], rax
0x10048df1e  lea     r8, [r11+20h]; lpExitTime
0x10048df22  lea     rdx, [r11+18h]; lpCreationTime
0x10048df26  call    cs:__imp_GetThreadTimes
0x10048df2c  mov     rax, [rsp+38h+arg_0]
0x10048df31  test    rbx, rbx
0x10048df34  jnz     short loc_10048DF72
0x10048df36  call    cs:__imp__errno
0x10048df3c  mov     dword ptr [rax], 16h
0x10048df42  call    cs:__imp__invalid_parameter_noinfo
0x10048df48  lea     rcx, [rbx+8]
0x10048df4c  mov     rax, [rsp+38h+arg_8]
0x10048df51  mov     [rcx], rax
0x10048df54  add     rbx, 10h
0x10048df58  jnz     short loc_10048DF92
0x10048df5a  call    cs:__imp__errno
0x10048df60  mov     dword ptr [rax], 16h
0x10048df66  call    cs:__imp__invalid_parameter_noinfo
0x10048df6c  add     rsp, 30h
0x10048df70  pop     rbx
0x10048df71  retn
0x10048df72  lea     rcx, [rbx+8]
0x10048df76  mov     [rbx], rax
0x10048df79  test    rcx, rcx
0x10048df7c  jnz     short loc_10048DF4C
0x10048df7e  call    cs:__imp__errno
0x10048df84  mov     dword ptr [rax], 16h
0x10048df8a  call    cs:__imp__invalid_parameter_noinfo
0x10048df90  jmp     short loc_10048DF54
0x10048df92  mov     rax, [rsp+38h+arg_10]
0x10048df97  mov     [rbx], rax
0x10048df9a  add     rsp, 30h
0x10048df9e  pop     rbx
0x10048df9f  retn
```
