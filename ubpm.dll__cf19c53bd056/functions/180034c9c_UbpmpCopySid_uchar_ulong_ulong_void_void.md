# UbpmpCopySid(uchar *,ulong,ulong *,void *,void * *)

- ea: `0x180034c9c`
- end: `0x180034cfd`
- name: `?UbpmpCopySid@@YAKPEAEKPEAKPEAXPEAPEAX@Z`
- size: `97`
- prototype: `unsigned int(unsigned __int8 *, unsigned int, unsigned int *, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f9f0`

## callees

- `0x180012530`
- `0x180034c9c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180034cd2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180034cd2`

## pseudocode

```c
__int64 __fastcall UbpmpCopySid(unsigned __int8 *a1, unsigned int a2, unsigned int *a3, void *a4, void **a5)
{
  DWORD LengthSid; // eax

  if ( a5 )
    *a5 = 0;
  if ( !a4 )
    return 0;
  LengthSid = GetLengthSid(a4);
  return UbpmpCopyArray<unsigned char>((__int64)a1, a2, a3, LengthSid, a4, a5);
}

```

## disassembly

```asm
0x180034c9c  push    rbx
0x180034c9e  push    rbp
0x180034c9f  push    rsi
0x180034ca0  push    rdi
0x180034ca1  push    r14
0x180034ca3  sub     rsp, 30h
0x180034ca7  mov     rbx, [rsp+58h+arg_20]
0x180034caf  mov     rdi, r9
0x180034cb2  mov     rsi, r8
0x180034cb5  mov     ebp, edx
0x180034cb7  mov     r14, rcx
0x180034cba  test    rbx, rbx
0x180034cbd  jz      short loc_180034CC6
0x180034cbf  mov     qword ptr [rbx], 0
0x180034cc6  test    rdi, rdi
0x180034cc9  jnz     short loc_180034CCF
0x180034ccb  xor     eax, eax
0x180034ccd  jmp     short loc_180034CF2
0x180034ccf  mov     rcx, rdi; pSid
0x180034cd2  call    cs:__imp_GetLengthSid
0x180034cd8  mov     [rsp+58h+var_30], rbx
0x180034cdd  mov     r8, rsi
0x180034ce0  mov     r9d, eax
0x180034ce3  mov     [rsp+58h+var_38], rdi
0x180034ce8  mov     edx, ebp
0x180034cea  mov     rcx, r14
0x180034ced  call    ??$UbpmpCopyArray@E@@YAKPEAEKPEAKKPEBEPEAPEAE@Z; UbpmpCopyArray<uchar>(uchar *,ulong,ulong *,ulong,uchar const *,uchar * *)
0x180034cf2  add     rsp, 30h
0x180034cf6  pop     r14
0x180034cf8  pop     rdi
0x180034cf9  pop     rsi
0x180034cfa  pop     rbp
0x180034cfb  pop     rbx
0x180034cfc  retn
```
