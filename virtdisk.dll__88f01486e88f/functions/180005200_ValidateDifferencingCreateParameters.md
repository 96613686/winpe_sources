# ValidateDifferencingCreateParameters

- ea: `0x180005200`
- end: `0x1800052e0`
- name: `ValidateDifferencingCreateParameters`
- size: `224`
- prototype: `__int64 __fastcall(unsigned int *, __int64, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002740`

## callees

- `0x180003930`
- `0x180005200`
- `0x180006f48`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052b5`

## pseudocode

```c
__int64 __fastcall ValidateDifferencingCreateParameters(unsigned int *a1, __int64 a2, void *a3)
{
  unsigned int v5; // edi
  __int64 v6; // [rsp+20h] [rbp-58h]
  int v7[2]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v8; // [rsp+48h] [rbp-30h]
  __int128 v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+68h] [rbp-10h]
  HANDLE hObject; // [rsp+88h] [rbp+10h] BYREF

  hObject = (HANDLE)-1LL;
  if ( !a2 )
    return 0;
  v10 = 0;
  v7[0] = 2;
  v7[1] = 1;
  v8 = 0;
  LODWORD(v6) = 1;
  v9 = 0;
  v5 = OpenVirtualDiskInternal(a1, a3, 0, 0, v6, v7, &hObject, 0);
  if ( !v5 )
    v5 = ValidateDifferencingRequestedSize(hObject, a2);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x180005200  push    rbx
0x180005202  sub     rsp, 70h
0x180005206  mov     [rsp+78h+hObject], 0FFFFFFFFFFFFFFFFh
0x180005212  mov     rax, r8
0x180005215  mov     rbx, rdx
0x180005218  test    rdx, rdx
0x18000521b  jnz     short loc_180005226
0x18000521d  xor     eax, eax
0x18000521f  add     rsp, 70h
0x180005223  pop     rbx
0x180005224  retn
0x180005226  mov     [rsp+78h+var_40], 0
0x18000522b  lea     rdx, [rsp+78h+hObject]
0x180005233  mov     [rsp+78h+var_48], rdx
0x180005238  xorps   xmm0, xmm0
0x18000523b  lea     rdx, [rsp+78h+var_38]
0x180005240  mov     [rsp+78h+arg_0], rdi
0x180005248  mov     [rsp+78h+var_50], rdx
0x18000524d  xorps   xmm1, xmm1
0x180005250  mov     rdx, rax
0x180005253  mov     [rsp+78h+var_10], 0
0x18000525b  xor     r9d, r9d
0x18000525e  mov     [rsp+78h+var_38], 2
0x180005266  xor     r8d, r8d
0x180005269  mov     [rsp+78h+var_34], 1
0x180005271  movdqu  [rsp+78h+var_30], xmm0
0x180005277  mov     dword ptr [rsp+78h+var_58], 1
0x18000527f  movdqu  [rsp+78h+var_20], xmm1
0x180005285  call    OpenVirtualDiskInternal
0x18000528a  mov     edi, eax
0x18000528c  test    eax, eax
0x18000528e  jnz     short loc_1800052A2
0x180005290  mov     rcx, [rsp+78h+hObject]
0x180005298  mov     rdx, rbx
0x18000529b  call    ValidateDifferencingRequestedSize
0x1800052a0  mov     edi, eax
0x1800052a2  cmp     [rsp+78h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800052ab  jz      short loc_1800052C1
0x1800052ad  mov     rcx, [rsp+78h+hObject]; hObject
0x1800052b5  call    cs:__imp_CloseHandle
0x1800052bc  nop     dword ptr [rax+rax+00h]
0x1800052c1  mov     eax, edi
0x1800052c3  mov     rdi, [rsp+78h+arg_0]
0x1800052cb  add     rsp, 70h
0x1800052cf  pop     rbx
0x1800052d0  retn
```
