# CACSecurityPage::PopulateMSAuthList(int *)

- ea: `0x18000c050`
- end: `0x18000c220`
- name: `?PopulateMSAuthList@CACSecurityPage@@AEAAJPEAH@Z`
- size: `464`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180007070`
- `0x18000739c`
- `0x18000c050`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000c099`
- `KERNEL32!HeapAlloc` at `0x18000c14f`
- `KERNEL32!HeapAlloc` at `0x18000c099`
- `KERNEL32!HeapAlloc` at `0x18000c14f`
- `KERNEL32!GetProcessHeap` at `0x18000c087`
- `KERNEL32!GetProcessHeap` at `0x18000c13d`
- `KERNEL32!GetProcessHeap` at `0x18000c087`
- `KERNEL32!GetProcessHeap` at `0x18000c13d`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::PopulateMSAuthList(CACSecurityPage *this, int *a2)
{
  __int64 v5; // r15
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rax
  int v8; // ebp
  unsigned int *v9; // rcx
  unsigned int v10; // esi
  unsigned int v11; // edx
  __int64 v12; // r8
  unsigned int v13; // r9d
  int v14; // eax
  __int64 v15; // r8
  HANDLE v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // rdi
  unsigned int v20; // eax
  __int64 v21; // rcx
  _BOOL8 v22; // r9
  _QWORD *v23; // rax

  if ( !*((_QWORD *)this + 3) )
    return 2147942413LL;
  v5 = *(_QWORD *)(*((_QWORD *)this + 5) + 552LL);
  *((_QWORD *)this + 4) = 0;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  *((_QWORD *)this + 4) = v7;
  if ( !v7 )
    return 2147942408LL;
  v7[3] = 0;
  v8 = 0;
  *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
  *(_QWORD *)(*((_QWORD *)this + 4) + 8LL) = 0;
  **((_QWORD **)this + 4) = 0;
  v9 = (unsigned int *)*((_QWORD *)this + 3);
  if ( *v9 )
  {
    v10 = 0;
    do
    {
      if ( !v8 )
      {
        if ( v9[2 * v10 + 1] != 1
          || (v11 = v9[2 * v10 + 2], ((v11 - 1) & 0xFFFFFEFB) != 0)
          || v11 == 261
          || (v8 = 1, *(_DWORD *)(v5 + 16) != 1) )
        {
          v8 = 0;
        }
      }
      v12 = **((_QWORD **)this + 4);
      if ( v12 )
      {
        v13 = v9[2 * v10 + 1];
        while ( 1 )
        {
          v14 = CACSecurityPage::Auth2AUIAuth(v9, v13, v12);
          v9 = *(unsigned int **)(v15 + 16);
          if ( v14 == v9[1] )
            break;
          v12 = *(_QWORD *)(v15 + 8);
          if ( !v12 )
            goto LABEL_16;
        }
      }
      else
      {
LABEL_16:
        v16 = GetProcessHeap();
        v17 = HeapAlloc(v16, 8u, 0x20u);
        v19 = v17;
        if ( !v17 )
          return 2147942408LL;
        v17[3] = 0;
        *v17 = 0;
        v17[1] = 0;
        v17[2] = 0;
        v20 = CACSecurityPage::Auth2AUIAuth(v10, *(unsigned int *)(*((_QWORD *)this + 3) + 8LL * v10 + 4), v18);
        v22 = 1;
        if ( v20 != 0x7FFFFFFF )
        {
          if ( v20 > 0xB || (v21 = 2376, !_bittest((const int *)&v21, v20)) )
            v22 = 0;
        }
        v19[2] = CACSecurityPage::CreateAuthInfo(v21, 1, v20, v22, 0, -1);
        v23 = (_QWORD *)*((_QWORD *)this + 4);
        if ( *v23 )
        {
          *v19 = v23[1];
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8LL) + 8LL) = v19;
          *(_QWORD *)(*((_QWORD *)this + 4) + 8LL) = v19;
        }
        else
        {
          v23[1] = v19;
          **((_QWORD **)this + 4) = v19;
        }
        ++*(_DWORD *)(*((_QWORD *)this + 4) + 16LL);
      }
      v9 = (unsigned int *)*((_QWORD *)this + 3);
      ++v10;
    }
    while ( v10 < *v9 );
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x18000c050  push    rbx
0x18000c052  push    rbp
0x18000c053  push    rsi
0x18000c054  push    rdi
0x18000c055  push    r12
0x18000c057  push    r14
0x18000c059  push    r15
0x18000c05b  sub     rsp, 30h
0x18000c05f  xor     r12d, r12d
0x18000c062  mov     r14, rdx
0x18000c065  mov     rbx, rcx
0x18000c068  cmp     [rcx+18h], r12
0x18000c06c  jnz     short loc_18000C078
0x18000c06e  mov     eax, 8007000Dh
0x18000c073  jmp     loc_18000C20A
0x18000c078  mov     rax, [rcx+28h]
0x18000c07c  mov     r15, [rax+228h]
0x18000c083  mov     [rcx+20h], r12
0x18000c087  call    cs:__imp_GetProcessHeap
0x18000c08d  mov     edx, 8; dwFlags
0x18000c092  mov     rcx, rax; hHeap
0x18000c095  lea     r8d, [rdx+18h]; dwBytes
0x18000c099  call    cs:__imp_HeapAlloc
0x18000c09f  mov     [rbx+20h], rax
0x18000c0a3  test    rax, rax
0x18000c0a6  jz      loc_18000C219
0x18000c0ac  mov     [rax+18h], r12
0x18000c0b0  mov     ebp, r12d
0x18000c0b3  mov     rax, [rbx+20h]
0x18000c0b7  mov     [rax+10h], r12d
0x18000c0bb  mov     rax, [rbx+20h]
0x18000c0bf  mov     [rax+8], r12
0x18000c0c3  mov     rax, [rbx+20h]
0x18000c0c7  mov     [rax], r12
0x18000c0ca  mov     rcx, [rbx+18h]
0x18000c0ce  cmp     [rcx], r12d
0x18000c0d1  jbe     loc_18000C204
0x18000c0d7  mov     esi, r12d
0x18000c0da  test    ebp, ebp
0x18000c0dc  jnz     short loc_18000C10C
0x18000c0de  mov     eax, esi
0x18000c0e0  cmp     dword ptr [rcx+rax*8+4], 1
0x18000c0e5  jnz     short loc_18000C109
0x18000c0e7  mov     edx, [rcx+rax*8+8]
0x18000c0eb  lea     eax, [rdx-1]
0x18000c0ee  test    eax, 0FFFFFEFBh
0x18000c0f3  jnz     short loc_18000C109
0x18000c0f5  cmp     edx, 105h
0x18000c0fb  jz      short loc_18000C109
0x18000c0fd  cmp     dword ptr [r15+10h], 1
0x18000c102  mov     ebp, 1
0x18000c107  jz      short loc_18000C10C
0x18000c109  mov     ebp, r12d
0x18000c10c  mov     rax, [rbx+20h]
0x18000c110  mov     r8, [rax]
0x18000c113  test    r8, r8
0x18000c116  jz      short loc_18000C13D
0x18000c118  mov     eax, esi
0x18000c11a  mov     r9d, [rcx+rax*8+4]
0x18000c11f  mov     edx, r9d
0x18000c122  call    ?Auth2AUIAuth@CACSecurityPage@@AEAA?AW4AUI_DOT11_AUTH_ALGORITHM@@W4_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::Auth2AUIAuth(_DOT11_AUTH_ALGORITHM)
0x18000c127  mov     rcx, [r8+10h]
0x18000c12b  cmp     eax, [rcx+4]
0x18000c12e  jz      loc_18000C1F6
0x18000c134  mov     r8, [r8+8]
0x18000c138  test    r8, r8
0x18000c13b  jnz     short loc_18000C11F
0x18000c13d  call    cs:__imp_GetProcessHeap
0x18000c143  mov     edx, 8; dwFlags
0x18000c148  mov     rcx, rax; hHeap
0x18000c14b  lea     r8d, [rdx+18h]; dwBytes
0x18000c14f  call    cs:__imp_HeapAlloc
0x18000c155  mov     rdi, rax
0x18000c158  test    rax, rax
0x18000c15b  jz      loc_18000C219
0x18000c161  mov     [rax+18h], r12
0x18000c165  mov     [rax], r12
0x18000c168  mov     [rax+8], r12
0x18000c16c  mov     [rax+10h], r12
0x18000c170  mov     rdx, [rbx+18h]
0x18000c174  mov     ecx, esi
0x18000c176  mov     edx, [rdx+rcx*8+4]
0x18000c17a  call    ?Auth2AUIAuth@CACSecurityPage@@AEAA?AW4AUI_DOT11_AUTH_ALGORITHM@@W4_DOT11_AUTH_ALGORITHM@@@Z; CACSecurityPage::Auth2AUIAuth(_DOT11_AUTH_ALGORITHM)
0x18000c17f  cmp     eax, 7FFFFFFFh
0x18000c184  jz      short loc_18000C19A
0x18000c186  cmp     eax, 0Bh
0x18000c189  ja      short loc_18000C195
0x18000c18b  mov     ecx, 948h
0x18000c190  bt      ecx, eax
0x18000c193  jb      short loc_18000C19A
0x18000c195  mov     r9d, r12d
0x18000c198  jmp     short loc_18000C1A0
0x18000c19a  mov     r9d, 1
0x18000c1a0  mov     [rsp+68h+var_40], 0FFFFFFFFh
0x18000c1a8  mov     r8d, eax
0x18000c1ab  mov     edx, 1
0x18000c1b0  mov     [rsp+68h+var_48], r12d
0x18000c1b5  call    ?CreateAuthInfo@CACSecurityPage@@AEAAPEAU_AUI_AUTH_INFO@@HW4AUI_DOT11_AUTH_ALGORITHM@@HHK@Z; CACSecurityPage::CreateAuthInfo(int,AUI_DOT11_AUTH_ALGORITHM,int,int,ulong)
0x18000c1ba  mov     [rdi+10h], rax
0x18000c1be  mov     rax, [rbx+20h]
0x18000c1c2  cmp     [rax], r12
0x18000c1c5  jnz     short loc_18000C1D4
0x18000c1c7  mov     [rax+8], rdi
0x18000c1cb  mov     rax, [rbx+20h]
0x18000c1cf  mov     [rax], rdi
0x18000c1d2  jmp     short loc_18000C1EF
0x18000c1d4  mov     rax, [rax+8]
0x18000c1d8  mov     [rdi], rax
0x18000c1db  mov     rax, [rbx+20h]
0x18000c1df  mov     rcx, [rax+8]
0x18000c1e3  mov     [rcx+8], rdi
0x18000c1e7  mov     rax, [rbx+20h]
0x18000c1eb  mov     [rax+8], rdi
0x18000c1ef  mov     rax, [rbx+20h]
0x18000c1f3  inc     dword ptr [rax+10h]
0x18000c1f6  mov     rcx, [rbx+18h]
0x18000c1fa  inc     esi
0x18000c1fc  cmp     esi, [rcx]
0x18000c1fe  jb      loc_18000C0DA
0x18000c204  mov     [r14], ebp
0x18000c207  mov     eax, r12d
0x18000c20a  add     rsp, 30h
0x18000c20e  pop     r15
0x18000c210  pop     r14
0x18000c212  pop     r12
0x18000c214  pop     rdi
0x18000c215  pop     rsi
0x18000c216  pop     rbp
0x18000c217  pop     rbx
0x18000c218  retn
0x18000c219  mov     eax, 80070008h
0x18000c21e  jmp     short loc_18000C20A
```
