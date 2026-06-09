# OncRpcMsgpAllocateMsgCallAndBuffer

- ea: `0x140003bd4`
- end: `0x140003cae`
- name: `OncRpcMsgpAllocateMsgCallAndBuffer`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140002288`

## callees

- `0x140001020`
- `0x140003bd4`
- `0x140015b40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003c91`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003c91`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003be7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003be7`

## pseudocode

```c
_DWORD *__fastcall OncRpcMsgpAllocateMsgCallAndBuffer(int a1)
{
  _DWORD *result; // rax
  _DWORD *v3; // rbx
  char *v4; // [rsp+48h] [rbp+10h] BYREF

  result = ExAllocateFromNPagedLookasideList(&stru_14001A700);
  v3 = result;
  if ( result )
  {
    memset(result, 0, 0x460u);
    *v3 = 1196641618;
    v3[1] = 0;
    v4 = (char *)(v3 + 8);
    *((_WORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 6) = 0;
    v3[8] = 1128677970;
    v3[9] = 0;
    *((_WORD *)v3 + 20) = 0;
    *((_QWORD *)v3 + 8) = v3 + 14;
    *((_QWORD *)v3 + 7) = v3 + 14;
    *((_QWORD *)v3 + 9) = 0;
    *((_QWORD *)v3 + 10) = 0;
    v3[22] = 0;
    v3[64] |= 4u;
    if ( (int)OncRpcBufMgrAllocate((unsigned int)&v4, a1, 4, 0, 0) < 0 )
    {
      ExFreeToNPagedLookasideList(&stru_14001A700, v3);
      return 0;
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x140003bd4  mov     [rsp+arg_0], rbx
0x140003bd9  push    rdi
0x140003bda  sub     rsp, 30h
0x140003bde  mov     edi, ecx
0x140003be0  lea     rcx, stru_14001A700; Lookaside
0x140003be7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140003bee  nop     dword ptr [rax+rax+00h]
0x140003bf3  mov     rbx, rax
0x140003bf6  test    rax, rax
0x140003bf9  jz      loc_140003CA2
0x140003bff  xor     edx, edx; Val
0x140003c01  mov     r8d, 460h; Size
0x140003c07  mov     rcx, rbx; void *
0x140003c0a  call    memset
0x140003c0f  mov     dword ptr [rbx], 47534D52h
0x140003c15  lea     rdx, [rbx+20h]
0x140003c19  mov     dword ptr [rbx+4], 0
0x140003c20  lea     rcx, [rsp+38h+arg_8]
0x140003c25  xor     eax, eax
0x140003c27  mov     [rsp+38h+arg_8], rdx
0x140003c2c  mov     [rbx+8], ax
0x140003c30  mov     r8d, 4
0x140003c36  mov     [rdx+10h], rax
0x140003c3a  xor     r9d, r9d
0x140003c3d  mov     dword ptr [rdx], 43464252h
0x140003c43  mov     [rdx+4], eax
0x140003c46  mov     [rdx+8], ax
0x140003c4a  lea     rax, [rdx+18h]
0x140003c4e  mov     [rax+8], rax
0x140003c52  mov     [rax], rax
0x140003c55  mov     qword ptr [rdx+28h], 0
0x140003c5d  mov     qword ptr [rdx+30h], 0
0x140003c65  mov     dword ptr [rdx+38h], 0
0x140003c6c  mov     edx, edi
0x140003c6e  or      [rbx+100h], r8d
0x140003c75  mov     [rsp+38h+var_18], 0
0x140003c7e  call    OncRpcBufMgrAllocate
0x140003c83  test    eax, eax
0x140003c85  jns     short loc_140003C9F
0x140003c87  mov     rdx, rbx; Entry
0x140003c8a  lea     rcx, stru_14001A700; Lookaside
0x140003c91  call    cs:__imp_ExFreeToNPagedLookasideList
0x140003c98  nop     dword ptr [rax+rax+00h]
0x140003c9d  xor     ebx, ebx
0x140003c9f  mov     rax, rbx
0x140003ca2  mov     rbx, [rsp+38h+arg_0]
0x140003ca7  add     rsp, 30h
0x140003cab  pop     rdi
0x140003cac  retn
```
