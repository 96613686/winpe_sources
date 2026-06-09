# CiHotpatchGetHotpatchTableOffsetFromLoadConfig

- ea: `0x180046edc`
- end: `0x180046f36`
- name: `CiHotpatchGetHotpatchTableOffsetFromLoadConfig`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180013130`

## callees

- `0x180046edc`

## pseudocode

```c
__int64 __fastcall CiHotpatchGetHotpatchTableOffsetFromLoadConfig(
        char a1,
        unsigned int *a2,
        unsigned int a3,
        _DWORD *a4)
{
  __int64 v6; // rcx
  unsigned int v7; // eax

  if ( a3 < 4 )
    return 3221226021LL;
  v6 = a1 != 0 ? 0x5C : 0;
  v7 = a1 != 0 ? 244 : 152;
  if ( *a2 < v7 || a3 < v7 )
    return 3221226021LL;
  *a4 = *(unsigned int *)((char *)a2 + v6 + 148);
  return 0;
}

```

## disassembly

```asm
0x180046edc  sub     rsp, 18h
0x180046ee0  mov     r10b, cl
0x180046ee3  cmp     r8d, 4
0x180046ee7  jnb     short loc_180046EF0
0x180046ee9  mov     eax, 0C0000225h
0x180046eee  jmp     short loc_180046F30
0x180046ef0  mov     al, r10b
0x180046ef3  neg     al
0x180046ef5  sbb     rcx, rcx
0x180046ef8  and     ecx, 5Ch
0x180046efb  neg     r10b
0x180046efe  sbb     eax, eax
0x180046f00  and     eax, 5Ch
0x180046f03  add     eax, 98h
0x180046f08  cmp     [rdx], eax
0x180046f0a  jb      short loc_180046F23
0x180046f0c  cmp     r8d, eax
0x180046f0f  jb      short loc_180046F23
0x180046f11  mov     eax, [rcx+rdx+94h]
0x180046f18  mov     [rsp+18h+var_14], eax
0x180046f1c  mov     [r9], eax
0x180046f1f  xor     eax, eax
0x180046f21  jmp     short loc_180046F30
0x180046f23  mov     eax, 0C0000225h
0x180046f28  mov     [rsp+18h+var_18], eax
0x180046f2b  jmp     short loc_180046F30
0x180046f2d  mov     [rsp+18h+var_18], eax
0x180046f30  add     rsp, 18h
0x180046f34  retn
```
