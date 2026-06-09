# UnlinkConvFromOthers(tagCONV_INFO *,int)

- ea: `0x18005e60c`
- end: `0x18005e7f1`
- name: `?UnlinkConvFromOthers@@YAXPEAUtagCONV_INFO@@H@Z`
- size: `485`
- prototype: `void __fastcall(struct tagCONV_INFO *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005e380`

## callees

- `0x1800060e0`
- `0x18000bd00`
- `0x180016310`
- `0x18005e60c`

## import_xrefs

- `win32u!NtUserDestroyWindow` at `0x18005e6df`
- `win32u!NtUserDestroyWindow` at `0x18005e6df`
- `ntdll!RtlEnterCriticalSection` at `0x18005e6ec`
- `ntdll!RtlEnterCriticalSection` at `0x18005e6ec`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e6d5`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e6d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e6ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e6ab`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e7a4`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e7b7`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e7a4`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e7b7`

## pseudocode

```c
void __fastcall UnlinkConvFromOthers(HWND *a1, int a2)
{
  int v4; // edi
  HWND *v5; // rsi
  struct tagCONV_INFO *WindowLongPtrW; // rax
  HWND v7; // r14
  struct tagCONV_INFO *v8; // r8
  HWND v9; // r8
  int i; // edx
  __int64 v11; // rdi
  HWND v12; // rax
  bool v13; // zf
  HWND v14; // rax
  char *v15; // rcx
  __int16 v16; // ax
  int v17; // ecx
  int v18; // eax
  unsigned __int64 v19; // rcx
  int *v20; // rdx
  int v21; // ecx
  __int64 v22; // r8

  v4 = 0;
  v5 = 0;
  WindowLongPtrW = (struct tagCONV_INFO *)GetWindowLongPtrW(a1[6], 0);
  v7 = (HWND)WindowLongPtrW;
  while ( 1 )
  {
    v8 = WindowLongPtrW;
    if ( !WindowLongPtrW )
      break;
    v17 = v4 + 1;
    WindowLongPtrW = *(struct tagCONV_INFO **)WindowLongPtrW;
    if ( ((*((_DWORD *)v8 + 6) >> 7) & 7) == 7 )
      v17 = v4;
    v4 = v17;
    if ( WindowLongPtrW == (struct tagCONV_INFO *)a1 )
      v5 = (HWND *)v8;
  }
  if ( !a2 )
  {
    v18 = v4 - 1;
    if ( ((*((_DWORD *)a1 + 6) >> 7) & 7) == 7 )
      v18 = v4;
    v4 = v18;
    if ( v5 )
    {
      *v5 = *a1;
    }
    else
    {
      v7 = *a1;
      SetWindowLongPtrW(a1[6], 0, (LONG_PTR)*a1);
    }
  }
  if ( !v4 )
  {
    if ( ((_BYTE)a1[7] & 0x10) != 0 )
    {
      v19 = (unsigned __int64)a1[15];
      if ( v19 )
      {
        v20 = (int *)*((_QWORD *)aHandleEntry + 2 * ((v19 >> 10) & 0x3FFF) + 1);
        v21 = 0;
        v22 = *v20;
        while ( v21 < (int)v22 )
        {
          if ( *(HWND *)&v20[2 * v21 + 2] == a1[6] )
          {
            *v20 = v22 - 1;
            *(_QWORD *)&v20[2 * v21 + 2] = *(_QWORD *)&v20[2 * v22];
            break;
          }
          ++v21;
        }
      }
    }
    else
    {
      v9 = a1[1];
      for ( i = 0; i < *((__int16 *)v9 + 52); ++i )
      {
        v11 = 2LL * i;
        if ( *(HWND *)(*((_QWORD *)v9 + 12) + 16LL * i + 8) == a1[6] )
        {
          if ( (GetAppCompatFlags2(39168) & 0x2000) != 0 )
          {
            DeleteAtom(*(_WORD *)(*((_QWORD *)a1[1] + 12) + 8 * v11));
            DeleteAtom(*(_WORD *)(*((_QWORD *)a1[1] + 12) + 8 * v11 + 2));
          }
          v12 = a1[1];
          v13 = (*((_WORD *)v12 + 52))-- == 1;
          v14 = a1[1];
          v15 = (char *)*((_QWORD *)v14 + 12);
          if ( v13 )
          {
            LocalFree(v15);
            *((_QWORD *)a1[1] + 12) = 0;
          }
          else
          {
            *(_OWORD *)&v15[8 * v11] = *(_OWORD *)&v15[16 * *((__int16 *)v14 + 52)];
          }
          break;
        }
      }
    }
  }
  v16 = *((_WORD *)a1 + 28);
  if ( (v16 & 0x10) != 0 )
  {
    a1[15] = 0;
    *((_WORD *)a1 + 28) = v16 & 0xFFBF;
  }
  if ( !v7 )
  {
    RtlLeaveCriticalSection(&gcsDDEML);
    NtUserDestroyWindow(a1[6]);
    RtlEnterCriticalSection(&gcsDDEML);
  }
}

```

## disassembly

```asm
0x18005e60c  mov     [rsp+arg_0], rbx
0x18005e611  mov     [rsp+arg_10], rbp
0x18005e616  push    rsi
0x18005e617  push    rdi
0x18005e618  push    r14
0x18005e61a  sub     rsp, 20h
0x18005e61e  mov     ebp, edx
0x18005e620  mov     rbx, rcx
0x18005e623  mov     rcx, [rcx+30h]; hWnd
0x18005e627  xor     edx, edx; nIndex
0x18005e629  xor     edi, edi
0x18005e62b  xor     esi, esi
0x18005e62d  call    GetWindowLongPtrW
0x18005e632  mov     r14, rax
0x18005e635  mov     r8, rax
0x18005e638  test    rax, rax
0x18005e63b  jnz     loc_18005E705
0x18005e641  test    ebp, ebp
0x18005e643  jz      loc_18005E72A
0x18005e649  test    edi, edi
0x18005e64b  jnz     short loc_18005E6BD
0x18005e64d  test    byte ptr [rbx+38h], 10h
0x18005e651  jnz     loc_18005E761
0x18005e657  mov     r8, [rbx+8]
0x18005e65b  xor     edx, edx
0x18005e65d  movsx   r9d, word ptr [r8+68h]
0x18005e662  cmp     edx, r9d
0x18005e665  jge     short loc_18005E6BD
0x18005e667  mov     rcx, [r8+60h]
0x18005e66b  mov     rax, [rbx+30h]
0x18005e66f  movsxd  rdi, edx
0x18005e672  add     rdi, rdi
0x18005e675  cmp     [rcx+rdi*8+8], rax
0x18005e67a  jnz     loc_18005E791
0x18005e680  mov     ecx, 9900h
0x18005e685  call    GetAppCompatFlags2
0x18005e68a  bt      eax, 0Dh
0x18005e68e  jb      loc_18005E798
0x18005e694  mov     rax, [rbx+8]
0x18005e698  sub     word ptr [rax+68h], 1
0x18005e69d  mov     rax, [rbx+8]
0x18005e6a1  mov     rcx, [rax+60h]; hMem
0x18005e6a5  jnz     loc_18005E7C2
0x18005e6ab  call    cs:__imp_LocalFree
0x18005e6b1  mov     rax, [rbx+8]
0x18005e6b5  mov     qword ptr [rax+60h], 0
0x18005e6bd  movzx   eax, word ptr [rbx+38h]
0x18005e6c1  test    al, 10h
0x18005e6c3  jnz     loc_18005E7D8
0x18005e6c9  test    r14, r14
0x18005e6cc  jnz     short loc_18005E6F2
0x18005e6ce  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18005e6d5  call    cs:__imp_RtlLeaveCriticalSection
0x18005e6db  mov     rcx, [rbx+30h]
0x18005e6df  call    cs:__imp_NtUserDestroyWindow
0x18005e6e5  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18005e6ec  call    cs:__imp_RtlEnterCriticalSection
0x18005e6f2  mov     rbx, [rsp+38h+arg_0]
0x18005e6f7  mov     rbp, [rsp+38h+arg_10]
0x18005e6fc  add     rsp, 20h
0x18005e700  pop     r14
0x18005e702  pop     rdi
0x18005e703  pop     rsi
0x18005e704  retn
0x18005e705  mov     edx, [r8+18h]
0x18005e709  lea     ecx, [rdi+1]
0x18005e70c  mov     rax, [r8]
0x18005e70f  shr     rdx, 7
0x18005e713  and     edx, 7
0x18005e716  cmp     dl, 7
0x18005e719  cmovz   ecx, edi
0x18005e71c  cmp     rax, rbx
0x18005e71f  mov     edi, ecx
0x18005e721  cmovz   rsi, r8
0x18005e725  jmp     loc_18005E635
0x18005e72a  mov     ecx, [rbx+18h]
0x18005e72d  lea     eax, [rdi-1]
0x18005e730  shr     rcx, 7
0x18005e734  and     ecx, 7
0x18005e737  cmp     cl, 7
0x18005e73a  cmovz   eax, edi
0x18005e73d  mov     edi, eax
0x18005e73f  mov     rax, [rbx]
0x18005e742  test    rsi, rsi
0x18005e745  jnz     loc_1800A0384
0x18005e74b  mov     rcx, [rbx+30h]; hWnd
0x18005e74f  mov     r8, rax; dwNewLong
0x18005e752  xor     edx, edx; nIndex
0x18005e754  mov     r14, rax
0x18005e757  call    SetWindowLongPtrW
0x18005e75c  jmp     loc_18005E649
0x18005e761  mov     rcx, [rbx+78h]
0x18005e765  test    rcx, rcx
0x18005e768  jz      loc_18005E6BD
0x18005e76e  mov     rax, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x18005e775  shr     rcx, 0Ah
0x18005e779  and     ecx, 3FFFh
0x18005e77f  add     rcx, rcx
0x18005e782  mov     rdx, [rax+rcx*8+8]
0x18005e787  xor     ecx, ecx
0x18005e789  movsxd  r8, dword ptr [rdx]
0x18005e78c  jmp     loc_1800A038C
0x18005e791  inc     edx
0x18005e793  jmp     loc_18005E662
0x18005e798  mov     rax, [rbx+8]
0x18005e79c  mov     rcx, [rax+60h]
0x18005e7a0  movzx   ecx, word ptr [rcx+rdi*8]; nAtom
0x18005e7a4  call    cs:__imp_DeleteAtom
0x18005e7aa  mov     rax, [rbx+8]
0x18005e7ae  mov     rcx, [rax+60h]
0x18005e7b2  movzx   ecx, word ptr [rcx+rdi*8+2]; nAtom
0x18005e7b7  call    cs:__imp_DeleteAtom
0x18005e7bd  jmp     loc_18005E694
0x18005e7c2  movsx   rax, word ptr [rax+68h]
0x18005e7c7  add     rax, rax
0x18005e7ca  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18005e7ce  movdqu  xmmword ptr [rcx+rdi*8], xmm0
0x18005e7d3  jmp     loc_18005E6BD
0x18005e7d8  mov     ecx, 0FFBFh
0x18005e7dd  mov     qword ptr [rbx+78h], 0
0x18005e7e5  and     ax, cx
0x18005e7e8  mov     [rbx+38h], ax
0x18005e7ec  jmp     loc_18005E6C9
0x1800a0384  mov     [rsi], rax
0x1800a0387  jmp     loc_18005E649
0x1800a038c  cmp     ecx, r8d
0x1800a038f  jge     loc_18005E6BD
0x1800a0395  mov     rax, [rbx+30h]
0x1800a0399  movsxd  r9, ecx
0x1800a039c  cmp     [rdx+r9*8+8], rax
0x1800a03a1  jz      short loc_1800A03A7
0x1800a03a3  inc     ecx
0x1800a03a5  jmp     short loc_1800A038C
0x1800a03a7  lea     eax, [r8-1]
0x1800a03ab  mov     [rdx], eax
0x1800a03ad  mov     rcx, [rdx+r8*8]
0x1800a03b1  mov     [rdx+r9*8+8], rcx
0x1800a03b6  jmp     loc_18005E6BD
```
