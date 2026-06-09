# CSPList<CTnMultiResNode *,CTnMultiResNode *>::RemoveHead(void)

- ea: `0x18000e118`
- end: `0x18000e151`
- name: `?RemoveHead@?$CSPList@PEAVCTnMultiResNode@@PEAV1@@@QEAAPEAVCTnMultiResNode@@XZ`
- size: `57`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009930`
- `0x18000a298`
- `0x18000a614`
- `0x18000aad0`
- `0x18000af70`
- `0x18000d1c0`
- `0x18000d8d4`

## callees

- `0x18000e118`

## pseudocode

```c
__int64 __fastcall CSPList<CTnMultiResNode *,CTnMultiResNode *>::RemoveHead(__int64 **a1)
{
  __int64 *v1; // rdx
  __int64 *v3; // rcx
  __int64 v4; // r8

  v1 = *a1;
  v3 = (__int64 *)**a1;
  v4 = v1[2];
  *a1 = v3;
  if ( v3 )
    v3[1] = 0;
  else
    a1[1] = 0;
  *v1 = (__int64)a1[3];
  --*((_DWORD *)a1 + 4);
  a1[3] = v1;
  return v4;
}

```

## disassembly

```asm
0x18000e118  mov     rdx, [rcx]
0x18000e11b  mov     rax, rcx
0x18000e11e  mov     rcx, [rdx]
0x18000e121  mov     r8, [rdx+10h]
0x18000e125  mov     [rax], rcx
0x18000e128  test    rcx, rcx
0x18000e12b  jz      short loc_18000E137
0x18000e12d  mov     qword ptr [rcx+8], 0
0x18000e135  jmp     short loc_18000E13F
0x18000e137  mov     qword ptr [rax+8], 0
0x18000e13f  mov     rcx, [rax+18h]
0x18000e143  mov     [rdx], rcx
0x18000e146  dec     dword ptr [rax+10h]
0x18000e149  mov     [rax+18h], rdx
0x18000e14d  mov     rax, r8
0x18000e150  retn
```
