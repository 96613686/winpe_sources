# SsiCredentialsUpdateFree

- ea: `0x180029bd0`
- end: `0x180029c8f`
- name: `SsiCredentialsUpdateFree`
- size: `191`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800277a0`

## callees

- `0x180009770`
- `0x180011fec`
- `0x180029bd0`

## pseudocode

```c
void __fastcall SsiCredentialsUpdateFree(HLOCAL hMem)
{
  PVOID *v2; // rcx
  __int64 v3; // rax
  void *v4; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hMem )
  {
    v3 = *((_QWORD *)hMem + 3);
    if ( v3 )
    {
      v4 = *(void **)(v3 + 8);
      if ( v4 )
      {
        DigestFreeMemory(v4);
        *(_QWORD *)(*((_QWORD *)hMem + 3) + 8LL) = 0;
        **((_DWORD **)hMem + 3) = 0;
      }
      DigestFreeMemory(*((HLOCAL *)hMem + 3));
      *((_QWORD *)hMem + 3) = 0;
    }
    DigestFreeMemory(hMem);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((char *)v2 + 28) < 0 )
    WPP_SF_(v2[2], 103, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
}

```

## disassembly

```asm
0x180029bd0  mov     [rsp+arg_0], rbx
0x180029bd5  push    rsi
0x180029bd6  sub     rsp, 20h
0x180029bda  mov     rbx, rcx
0x180029bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180029be4  lea     rsi, WPP_GLOBAL_Control
0x180029beb  cmp     rcx, rsi
0x180029bee  jz      short loc_180029C12
0x180029bf0  test    byte ptr [rcx+1Ch], 80h
0x180029bf4  jz      short loc_180029C12
0x180029bf6  mov     rcx, [rcx+10h]
0x180029bfa  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180029c01  mov     edx, 66h ; 'f'
0x180029c06  call    WPP_SF_
0x180029c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c12  test    rbx, rbx
0x180029c15  jz      short loc_180029C64
0x180029c17  mov     rax, [rbx+18h]
0x180029c1b  test    rax, rax
0x180029c1e  jz      short loc_180029C55
0x180029c20  mov     rcx, [rax+8]; hMem
0x180029c24  test    rcx, rcx
0x180029c27  jz      short loc_180029C44
0x180029c29  call    DigestFreeMemory
0x180029c2e  mov     rax, [rbx+18h]
0x180029c32  mov     qword ptr [rax+8], 0
0x180029c3a  mov     rax, [rbx+18h]
0x180029c3e  mov     dword ptr [rax], 0
0x180029c44  mov     rcx, [rbx+18h]; hMem
0x180029c48  call    DigestFreeMemory
0x180029c4d  mov     qword ptr [rbx+18h], 0
0x180029c55  mov     rcx, rbx; hMem
0x180029c58  call    DigestFreeMemory
0x180029c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c64  cmp     rcx, rsi
0x180029c67  jz      short loc_180029C84
0x180029c69  test    byte ptr [rcx+1Ch], 80h
0x180029c6d  jz      short loc_180029C84
0x180029c6f  mov     rcx, [rcx+10h]
0x180029c73  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180029c7a  mov     edx, 67h ; 'g'
0x180029c7f  call    WPP_SF_
0x180029c84  mov     rbx, [rsp+28h+arg_0]
0x180029c89  add     rsp, 20h
0x180029c8d  pop     rsi
0x180029c8e  retn
```
