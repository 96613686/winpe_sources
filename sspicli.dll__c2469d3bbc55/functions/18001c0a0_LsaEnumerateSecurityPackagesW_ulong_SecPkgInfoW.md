# LsaEnumerateSecurityPackagesW(ulong *,_SecPkgInfoW * *)

- ea: `0x18001c0a0`
- end: `0x18001c122`
- name: `?LsaEnumerateSecurityPackagesW@@YAJPEAKPEAPEAU_SecPkgInfoW@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(unsigned int *, struct _SecPkgInfoW **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800011f0`
- `0x180002740`
- `0x180007c90`
- `0x18000c4f0`
- `0x18001c0a0`
- `0x180021328`

## pseudocode

```c
__int64 __fastcall LsaEnumerateSecurityPackagesW(unsigned int *a1, struct _SecPkgInfoW **a2)
{
  int v5; // eax
  struct _SecPkgInfoW *v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rcx
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v9 = 0;
  if ( !(unsigned int)SecpReserveVMSpots(1, &v9) )
    return 2148074240LL;
  v5 = SecpEnumeratePackages(a1, a2);
  v6 = *a2;
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( v6 )
    {
      LsaFreeReturnBuffer(v6);
      v8 = v9;
      *a2 = 0;
      SecpReleaseVMSpots(v8);
    }
  }
  else
  {
    SecpAddVMEx(v6, 0, &v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18001c0a0  mov     [rsp+arg_0], rbx
0x18001c0a5  push    rdi
0x18001c0a6  sub     rsp, 20h
0x18001c0aa  mov     rbx, rdx
0x18001c0ad  mov     qword ptr [rdx], 0
0x18001c0b4  mov     rdi, rcx
0x18001c0b7  mov     [rsp+28h+arg_8], 0
0x18001c0bf  lea     rdx, [rsp+28h+arg_8]
0x18001c0c4  mov     ecx, 1
0x18001c0c9  call    SecpReserveVMSpots
0x18001c0ce  test    eax, eax
0x18001c0d0  jnz     short loc_18001C0D9
0x18001c0d2  mov     eax, 80090300h
0x18001c0d7  jmp     short loc_18001C117
0x18001c0d9  mov     rdx, rbx
0x18001c0dc  mov     rcx, rdi
0x18001c0df  call    SecpEnumeratePackages
0x18001c0e4  mov     rcx, [rbx]; Buffer
0x18001c0e7  mov     edi, eax
0x18001c0e9  test    eax, eax
0x18001c0eb  js      short loc_18001C0FB
0x18001c0ed  lea     r8, [rsp+28h+arg_8]
0x18001c0f2  xor     edx, edx
0x18001c0f4  call    SecpAddVMEx
0x18001c0f9  jmp     short loc_18001C115
0x18001c0fb  test    rcx, rcx
0x18001c0fe  jz      short loc_18001C115
0x18001c100  call    LsaFreeReturnBuffer
0x18001c105  mov     ecx, [rsp+28h+arg_8]
0x18001c109  mov     qword ptr [rbx], 0
0x18001c110  call    SecpReleaseVMSpots
0x18001c115  mov     eax, edi
0x18001c117  mov     rbx, [rsp+28h+arg_0]
0x18001c11c  add     rsp, 20h
0x18001c120  pop     rdi
0x18001c121  retn
```
