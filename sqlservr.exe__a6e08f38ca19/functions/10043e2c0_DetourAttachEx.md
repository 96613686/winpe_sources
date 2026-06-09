# DetourAttachEx

- ea: `0x10043e2c0`
- end: `0x10043e6f3`
- name: `DetourAttachEx`
- size: `1075`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x10043cc10`
- `0x10043d2c0`

## callees

- `0x100401580`
- `0x100402880`
- `0x10043d670`
- `0x10043da50`
- `0x10043dcf0`
- `0x10043e2c0`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10043e6b5`
- `KERNEL32!HeapFree` at `0x10043e6b5`
- `KERNEL32!GetProcessHeap` at `0x10043e3c6`
- `KERNEL32!GetProcessHeap` at `0x10043e6a7`
- `KERNEL32!GetProcessHeap` at `0x10043e3c6`
- `KERNEL32!GetProcessHeap` at `0x10043e6a7`
- `KERNEL32!VirtualProtect` at `0x10043e5fb`
- `KERNEL32!VirtualProtect` at `0x10043e5fb`
- `KERNEL32!SetLastError` at `0x10043e472`
- `KERNEL32!SetLastError` at `0x10043e472`
- `KERNEL32!HeapAlloc` at `0x10043e3d5`
- `KERNEL32!HeapAlloc` at `0x10043e3d5`
- `KERNEL32!GetLastError` at `0x10043e605`
- `KERNEL32!GetLastError` at `0x10043e605`
- `KERNEL32!GetCurrentThreadId` at `0x10043e328`
- `KERNEL32!GetCurrentThreadId` at `0x10043e328`

## pseudocode

```c
__int64 __fastcall DetourAttachEx(__int64 *a1, __int64 a2, __int64 *a3, unsigned __int8 **a4, __int64 *a5)
{
  _QWORD *v5; // r15
  DWORD LastError; // ebx
  __int64 result; // rax
  __int64 v12; // rcx
  __int64 v13; // rdi
  unsigned __int8 *v14; // r12
  __int64 v15; // rax
  HANDLE ProcessHeap; // rax
  __int64 v17; // rax
  char *v18; // r14
  unsigned int v19; // ebp
  unsigned __int8 *v20; // r8
  char *v21; // rsi
  char *v22; // rcx
  unsigned __int8 *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdx
  unsigned int v26; // r9d
  char v27; // r10
  unsigned __int64 v28; // rcx
  __int64 v29; // rdx
  bool v30; // zf
  unsigned __int64 v31; // rax
  signed int is_code_filler; // eax
  __int64 v33; // r8
  SIZE_T v34; // rbx
  __int64 v35; // rdx
  void *v36; // rcx
  size_t v37; // r8
  HANDLE v38; // rax
  int v39; // [rsp+20h] [rbp-F8h] BYREF
  DWORD flOldProtect; // [rsp+24h] [rbp-F4h] BYREF
  __int64 v41; // [rsp+28h] [rbp-F0h]
  __int64 v42; // [rsp+30h] [rbp-E8h]
  _QWORD v43[7]; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v44; // [rsp+78h] [rbp-A0h] BYREF
  char v45; // [rsp+80h] [rbp-98h] BYREF

  v5 = 0;
  v41 = (__int64)a1;
  LastError = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
    return 87;
  if ( dword_1004D3F60 != GetCurrentThreadId() )
    return 4317;
  result = (unsigned int)dword_1004D3F5C;
  if ( !dword_1004D3F5C )
  {
    if ( !a1 )
      return 6;
    v12 = *a1;
    if ( !*a1 )
    {
      qword_1004D3F70 = (__int64)a1;
      dword_1004D3F5C = 6;
      return 6;
    }
    v13 = 0;
    v14 = (unsigned __int8 *)DetourCodeFromPointer(v12, 0);
    v15 = DetourCodeFromPointer(a2, 0);
    v42 = v15;
    if ( (unsigned __int8 *)v15 == v14 )
    {
      if ( !dword_1004A3834 )
        goto LABEL_66;
      goto LABEL_71;
    }
    if ( a4 )
      *a4 = v14;
    if ( a5 )
      *a5 = v15;
    ProcessHeap = GetProcessHeap();
    v5 = HeapAlloc(ProcessHeap, 0, 0x30u);
    if ( v5 )
    {
      v17 = detour_alloc_trampoline(v14);
      v13 = v17;
      if ( v17 )
      {
        if ( a3 )
          *a3 = v17;
        v18 = (char *)(v17 + 30);
        *(_QWORD *)(v17 + 64) = 0;
        v19 = 0;
        v20 = v14;
        v21 = (char *)v17;
        while ( 1 )
        {
          v44 = 0;
          v39 = 0;
          v43[4] = &v44;
          v22 = &v45;
          v43[0] = 0;
          v43[1] = 0;
          if ( v21 )
            v22 = v21;
          v43[5] = &v39;
          v43[2] = 0;
          v23 = v20;
          if ( v20 )
          {
            v24 = (*((__int64 (__fastcall **)(_QWORD *, const struct CDetourDis::COPYENTRY near *const *, char *, unsigned __int8 *))&CDetourDis::s_rceCopyTable
                   + 2 * *v20
                   + 1))(
                    v43,
                    &CDetourDis::s_rceCopyTable + 2 * *v20,
                    v22,
                    v20);
          }
          else
          {
            SetLastError(0xDu);
            v24 = 0;
          }
          v20 = (unsigned __int8 *)v24;
          v25 = v19;
          v26 = v24 - (_DWORD)v14;
          v21 += v24 + v39 - (_QWORD)v23;
          ++v19;
          v27 = (_BYTE)v21 - v13;
          *(_BYTE *)(v25 + v13 + 64) = (8 * ((_BYTE)v21 - v13)) | (v24 - (_BYTE)v14) & 7;
          if ( v19 >= 8
            || (v28 = *v23, (unsigned __int8)(v28 + 62) <= 0x29u)
            && (v29 = 0x28040000403LL, _bittest64(&v29, (unsigned int)(v28 + 62))) )
          {
LABEL_47:
            if ( v26 >= 5 )
            {
LABEL_50:
              if ( v19 <= 8 )
              {
LABEL_51:
                if ( v21 > v18 )
                  __debugbreak();
                *v18 = v27;
                *(_BYTE *)(v13 + 62) = v26;
                v34 = v26;
                memmove((void *)(v13 + 32), v14, v26);
                if ( v34 > 0x19 )
                {
                  LastError = 6;
                  goto LABEL_66;
                }
                v35 = v13 + (unsigned __int8)*v18;
                *(_QWORD *)(v13 + 72) = &v14[v34];
                *(_QWORD *)(v13 + 80) = v42;
                *(_WORD *)v35 = 9727;
                v36 = (void *)(v35 + 6);
                v37 = (size_t)&v18[-v35 - 6];
                *(_DWORD *)(v35 + 2) = v13 - (v35 + 6) + 72;
                if ( v35 + 6 > (unsigned __int64)v18 )
                  v37 = 0;
                if ( v37 )
                {
                  LOBYTE(v35) = -52;
                  memset_0(v36, v35, v37);
                }
                flOldProtect = 0;
                if ( !VirtualProtect(v14, v34, 0x40u, &flOldProtect) )
                {
                  LastError = GetLastError();
                  goto LABEL_66;
                }
                v5[2] = v41;
                *((_DWORD *)v5 + 2) = 0;
                v5[4] = v13;
                v5[3] = v14;
                *((_DWORD *)v5 + 10) = flOldProtect;
                *v5 = lpMem;
                result = 0;
                lpMem = v5;
                return result;
              }
            }
            else
            {
              while ( 1 )
              {
                is_code_filler = detour_is_code_filler(v20);
                if ( !is_code_filler )
                  break;
                v20 = (unsigned __int8 *)(is_code_filler + v33);
                v26 = (_DWORD)v20 - (_DWORD)v14;
                if ( (unsigned int)((_DWORD)v20 - (_DWORD)v14) >= 5 )
                  goto LABEL_50;
              }
            }
            LastError = 9;
            if ( dword_1004A3834 )
              goto LABEL_67;
LABEL_66:
            dword_1004D3F5C = LastError;
            if ( v13 )
            {
LABEL_67:
              *(_OWORD *)v13 = 0;
              *(_OWORD *)(v13 + 16) = 0;
              *(_OWORD *)(v13 + 32) = 0;
              *(_OWORD *)(v13 + 48) = 0;
              *(_OWORD *)(v13 + 64) = 0;
              *(_OWORD *)(v13 + 80) = 0;
              *(_QWORD *)(v13 + 72) = *(_QWORD *)((v13 & 0xFFFFFFFFFFFF0000uLL) + 0x10);
              *(_QWORD *)((v13 & 0xFFFFFFFFFFFF0000uLL) + 0x10) = v13;
              if ( a3 )
                *a3 = 0;
            }
            if ( v5 )
            {
              v38 = GetProcessHeap();
              HeapFree(v38, 0, v5);
            }
LABEL_71:
            qword_1004D3F70 = v41;
            return LastError;
          }
          if ( (_BYTE)v28 == 0xF3 )
          {
            v30 = v23[1] == 0xC3;
            goto LABEL_44;
          }
          if ( (_BYTE)v28 == 0xFF )
            break;
          LOBYTE(v28) = v28 - 38;
          if ( (unsigned __int8)v28 <= 0x3Fu )
          {
            v31 = 0xC000000001010101uLL;
            if ( _bittest64((const __int64 *)&v31, v28) )
            {
              if ( v23[1] == 0xFF )
              {
                v30 = v23[2] == 37;
LABEL_44:
                if ( v30 )
                  goto LABEL_47;
              }
            }
          }
          if ( v26 >= 5 )
            goto LABEL_51;
        }
        v30 = v23[1] == 37;
        goto LABEL_44;
      }
    }
    else
    {
      v5 = 0;
    }
    LastError = 8;
    goto LABEL_66;
  }
  return result;
}

```

## disassembly

```asm
0x10043e2c0  push    rbx
0x10043e2c2  push    rbp
0x10043e2c3  push    rsi
0x10043e2c4  push    rdi
0x10043e2c5  push    r13
0x10043e2c7  push    r14
0x10043e2c9  push    r15
0x10043e2cb  sub     rsp, 0E0h
0x10043e2d2  mov     rax, cs:__security_cookie
0x10043e2d9  xor     rax, rsp
0x10043e2dc  mov     [rsp+118h+var_58], rax
0x10043e2e4  mov     r14, [rsp+118h+arg_20]
0x10043e2ec  xor     r15d, r15d
0x10043e2ef  mov     [rsp+118h+var_F0], rcx
0x10043e2f4  mov     rsi, r9
0x10043e2f7  mov     r13, r8
0x10043e2fa  mov     rbp, rdx
0x10043e2fd  mov     rdi, rcx
0x10043e300  mov     ebx, r15d
0x10043e303  test    r8, r8
0x10043e306  jz      short loc_10043E30B
0x10043e308  mov     [r8], r15
0x10043e30b  test    rsi, rsi
0x10043e30e  jz      short loc_10043E313
0x10043e310  mov     [r9], r15
0x10043e313  test    r14, r14
0x10043e316  jz      short loc_10043E31B
0x10043e318  mov     [r14], r15
0x10043e31b  test    rbp, rbp
0x10043e31e  jnz     short loc_10043E328
0x10043e320  lea     eax, [rbp+57h]
0x10043e323  jmp     loc_10043E6D1
0x10043e328  call    cs:__imp_GetCurrentThreadId
0x10043e32e  cmp     cs:dword_1004D3F60, eax
0x10043e334  jz      short loc_10043E340
0x10043e336  mov     eax, 10DDh
0x10043e33b  jmp     loc_10043E6D1
0x10043e340  mov     eax, cs:dword_1004D3F5C
0x10043e346  test    eax, eax
0x10043e348  jnz     loc_10043E6D1
0x10043e34e  test    rdi, rdi
0x10043e351  jnz     short loc_10043E35B
0x10043e353  lea     eax, [rdi+6]
0x10043e356  jmp     loc_10043E6D1
0x10043e35b  mov     rcx, [rdi]
0x10043e35e  test    rcx, rcx
0x10043e361  jnz     short loc_10043E37C
0x10043e363  mov     ebx, 6
0x10043e368  mov     cs:qword_1004D3F70, rdi
0x10043e36f  mov     cs:dword_1004D3F5C, ebx
0x10043e375  mov     eax, ebx
0x10043e377  jmp     loc_10043E6D1
0x10043e37c  xor     edx, edx
0x10043e37e  mov     [rsp+118h+var_40], r12
0x10043e386  mov     rdi, r15
0x10043e389  call    DetourCodeFromPointer
0x10043e38e  xor     edx, edx
0x10043e390  mov     rcx, rbp
0x10043e393  mov     r12, rax
0x10043e396  call    DetourCodeFromPointer
0x10043e39b  mov     [rsp+118h+var_E8], rax
0x10043e3a0  cmp     rax, r12
0x10043e3a3  jnz     short loc_10043E3B6
0x10043e3a5  cmp     cs:dword_1004A3834, ebx
0x10043e3ab  jnz     loc_10043E6BB
0x10043e3b1  jmp     loc_10043E65C
0x10043e3b6  test    rsi, rsi
0x10043e3b9  jz      short loc_10043E3BE
0x10043e3bb  mov     [rsi], r12
0x10043e3be  test    r14, r14
0x10043e3c1  jz      short loc_10043E3C6
0x10043e3c3  mov     [r14], rax
0x10043e3c6  call    cs:__imp_GetProcessHeap
0x10043e3cc  xor     edx, edx; dwFlags
0x10043e3ce  mov     rcx, rax; hHeap
0x10043e3d1  lea     r8d, [rdx+30h]; dwBytes
0x10043e3d5  call    cs:__imp_HeapAlloc
0x10043e3db  mov     r15, rax
0x10043e3de  test    rax, rax
0x10043e3e1  jz      loc_10043E654
0x10043e3e7  mov     rcx, r12
0x10043e3ea  call    detour_alloc_trampoline
0x10043e3ef  mov     rdi, rax
0x10043e3f2  test    rax, rax
0x10043e3f5  jz      loc_10043E657
0x10043e3fb  test    r13, r13
0x10043e3fe  jz      short loc_10043E404
0x10043e400  mov     [r13+0], rax
0x10043e404  xor     eax, eax
0x10043e406  lea     r14, [rdi+1Eh]
0x10043e40a  xor     ecx, ecx
0x10043e40c  mov     [rdi+40h], rax
0x10043e410  mov     ebp, ecx
0x10043e412  mov     r8, r12
0x10043e415  mov     rsi, rdi
0x10043e418  lea     rax, [rsp+118h+var_A0]
0x10043e41d  mov     [rsp+118h+var_A0], rcx
0x10043e422  mov     [rsp+118h+var_F8], ecx
0x10043e426  lea     rdx, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable
0x10043e42d  test    rsi, rsi
0x10043e430  mov     [rsp+118h+var_B8], rax
0x10043e435  lea     rcx, [rsp+118h+var_98]
0x10043e43d  mov     [rsp+118h+var_D8], 0
0x10043e446  lea     rax, [rsp+118h+var_F8]
0x10043e44b  mov     [rsp+118h+var_D0], 0
0x10043e454  cmovnz  rcx, rsi
0x10043e458  mov     [rsp+118h+var_B0], rax
0x10043e45d  mov     [rsp+118h+var_C8], 0
0x10043e466  mov     rbx, r8
0x10043e469  test    r8, r8
0x10043e46c  jnz     short loc_10043E47C
0x10043e46e  lea     ecx, [r8+0Dh]; dwErrCode
0x10043e472  call    cs:__imp_SetLastError
0x10043e478  xor     eax, eax
0x10043e47a  jmp     short loc_10043E498
0x10043e47c  movzx   eax, byte ptr [r8]
0x10043e480  mov     r9, r8
0x10043e483  shl     rax, 4
0x10043e487  mov     r8, rcx
0x10043e48a  add     rax, rdx
0x10043e48d  lea     rcx, [rsp+118h+var_D8]
0x10043e492  mov     rdx, rax
0x10043e495  call    qword ptr [rax+8]
0x10043e498  mov     r8, rax
0x10043e49b  mov     edx, ebp
0x10043e49d  movsxd  rax, [rsp+118h+var_F8]
0x10043e4a2  mov     r9d, r8d
0x10043e4a5  sub     rax, rbx
0x10043e4a8  sub     r9d, r12d
0x10043e4ab  add     rax, r8
0x10043e4ae  movzx   ecx, r9b
0x10043e4b2  add     rsi, rax
0x10043e4b5  and     cl, 7
0x10043e4b8  movzx   r10d, sil
0x10043e4bc  inc     ebp
0x10043e4be  sub     r10b, dil
0x10043e4c1  movzx   eax, r10b
0x10043e4c5  shl     al, 3
0x10043e4c8  or      cl, al
0x10043e4ca  mov     [rdx+rdi+40h], cl
0x10043e4ce  cmp     ebp, 8
0x10043e4d1  jnb     short loc_10043E534
0x10043e4d3  movzx   ecx, byte ptr [rbx]
0x10043e4d6  lea     eax, [rcx+3Eh]
0x10043e4d9  cmp     al, 29h ; ')'
0x10043e4db  ja      short loc_10043E4ED
0x10043e4dd  mov     rdx, 28040000403h
0x10043e4e7  bt      rdx, rax
0x10043e4eb  jb      short loc_10043E534
0x10043e4ed  cmp     cl, 0F3h
0x10043e4f0  jnz     short loc_10043E4F8
0x10043e4f2  cmp     byte ptr [rbx+1], 0C3h
0x10043e4f6  jmp     short loc_10043E525
0x10043e4f8  cmp     cl, 0FFh
0x10043e4fb  jnz     short loc_10043E503
0x10043e4fd  cmp     byte ptr [rbx+1], 25h ; '%'
0x10043e501  jmp     short loc_10043E525
0x10043e503  sub     cl, 26h ; '&'
0x10043e506  cmp     cl, 3Fh ; '?'
0x10043e509  ja      short loc_10043E527
0x10043e50b  mov     rax, 0C000000001010101h
0x10043e515  bt      rax, rcx
0x10043e519  jnb     short loc_10043E527
0x10043e51b  cmp     byte ptr [rbx+1], 0FFh
0x10043e51f  jnz     short loc_10043E527
0x10043e521  cmp     byte ptr [rbx+2], 25h ; '%'
0x10043e525  jz      short loc_10043E534
0x10043e527  cmp     r9d, 5
0x10043e52b  jnb     short loc_10043E56A
0x10043e52d  xor     ecx, ecx
0x10043e52f  jmp     loc_10043E418
0x10043e534  cmp     r9d, 5
0x10043e538  jnb     short loc_10043E561
0x10043e53a  nop     word ptr [rax+rax]
0x10043e53f  nop
0x10043e540  mov     rcx, r8; unsigned __int8 *
0x10043e543  call    ?detour_is_code_filler@@YAKPEAE@Z; detour_is_code_filler(uchar *)
0x10043e548  test    eax, eax
0x10043e54a  jz      loc_10043E644
0x10043e550  cdqe
0x10043e552  add     r8, rax
0x10043e555  mov     r9, r8
0x10043e558  sub     r9d, r12d
0x10043e55b  cmp     r9d, 5
0x10043e55f  jb      short loc_10043E540
0x10043e561  cmp     ebp, 8
0x10043e564  ja      loc_10043E644
0x10043e56a  cmp     rsi, r14
0x10043e56d  jbe     short loc_10043E570
0x10043e56f  int     3; Trap to Debugger
0x10043e570  lea     rcx, [rdi+20h]; void *
0x10043e574  mov     r8d, r9d; Size
0x10043e577  mov     rdx, r12; Src
0x10043e57a  mov     [r14], r10b
0x10043e57d  mov     [rdi+3Eh], r9b
0x10043e581  mov     ebx, r9d
0x10043e584  call    memmove
0x10043e589  cmp     rbx, 19h
0x10043e58d  jbe     short loc_10043E599
0x10043e58f  mov     ebx, 6
0x10043e594  jmp     loc_10043E65C
0x10043e599  movzx   edx, byte ptr [r14]
0x10043e59d  lea     rax, [rbx+r12]
0x10043e5a1  add     rdx, rdi
0x10043e5a4  mov     [rdi+48h], rax
0x10043e5a8  mov     rax, [rsp+118h+var_E8]
0x10043e5ad  mov     r8, r14
0x10043e5b0  mov     [rdi+50h], rax
0x10043e5b4  mov     esi, 0
0x10043e5b9  mov     eax, edi
0x10043e5bb  lea     rcx, [rdx+6]
0x10043e5bf  mov     word ptr [rdx], 25FFh
0x10043e5c4  sub     eax, ecx
0x10043e5c6  lea     rcx, [rdx+6]; void *
0x10043e5ca  sub     r8, rcx
0x10043e5cd  add     eax, 48h ; 'H'
0x10043e5d0  cmp     rcx, r14
0x10043e5d3  mov     [rdx+2], eax
0x10043e5d6  cmova   r8, rsi; Size
0x10043e5da  test    r8, r8
0x10043e5dd  jz      short loc_10043E5E6
0x10043e5df  mov     dl, 0CCh; Val
0x10043e5e1  call    memset_0
0x10043e5e6  lea     r9, [rsp+118h+flOldProtect]; lpflOldProtect
0x10043e5eb  mov     [rsp+118h+flOldProtect], esi
0x10043e5ef  mov     r8d, 40h ; '@'; flNewProtect
0x10043e5f5  mov     rdx, rbx; dwSize
0x10043e5f8  mov     rcx, r12; lpAddress
0x10043e5fb  call    cs:__imp_VirtualProtect
0x10043e601  test    eax, eax
0x10043e603  jnz     short loc_10043E60F
0x10043e605  call    cs:__imp_GetLastError
0x10043e60b  mov     ebx, eax
0x10043e60d  jmp     short loc_10043E65C
0x10043e60f  mov     rax, [rsp+118h+var_F0]
0x10043e614  mov     [r15+10h], rax
0x10043e618  mov     [r15+8], esi
0x10043e61c  mov     [r15+20h], rdi
0x10043e620  mov     [r15+18h], r12
0x10043e624  mov     eax, [rsp+118h+flOldProtect]
0x10043e628  mov     [r15+28h], eax
0x10043e62c  mov     rax, cs:lpMem
0x10043e633  mov     [r15], rax
0x10043e636  xor     eax, eax
0x10043e638  mov     cs:lpMem, r15
0x10043e63f  jmp     loc_10043E6C9
0x10043e644  cmp     cs:dword_1004A3834, 0
0x10043e64b  mov     ebx, 9
0x10043e650  jnz     short loc_10043E667
0x10043e652  jmp     short loc_10043E65C
0x10043e654  mov     r15, rax
0x10043e657  mov     ebx, 8
0x10043e65c  mov     cs:dword_1004D3F5C, ebx
0x10043e662  test    rdi, rdi
0x10043e665  jz      short loc_10043E6A2
0x10043e667  xorps   xmm0, xmm0
0x10043e66a  mov     rcx, rdi
0x10043e66d  movups  xmmword ptr [rdi], xmm0
0x10043e670  and     rcx, 0FFFFFFFFFFFF0000h
0x10043e677  movups  xmmword ptr [rdi+10h], xmm0
0x10043e67b  movups  xmmword ptr [rdi+20h], xmm0
0x10043e67f  movups  xmmword ptr [rdi+30h], xmm0
0x10043e683  movups  xmmword ptr [rdi+40h], xmm0
0x10043e687  movups  xmmword ptr [rdi+50h], xmm0
0x10043e68b  mov     rax, [rcx+10h]
0x10043e68f  mov     [rdi+48h], rax
0x10043e693  mov     [rcx+10h], rdi
0x10043e697  test    r13, r13
0x10043e69a  jz      short loc_10043E6A2
0x10043e69c  xor     eax, eax
0x10043e69e  mov     [r13+0], rax
0x10043e6a2  test    r15, r15
0x10043e6a5  jz      short loc_10043E6BB
0x10043e6a7  call    cs:__imp_GetProcessHeap
0x10043e6ad  mov     r8, r15; lpMem
0x10043e6b0  xor     edx, edx; dwFlags
0x10043e6b2  mov     rcx, rax; hHeap
0x10043e6b5  call    cs:__imp_HeapFree
0x10043e6bb  mov     rax, [rsp+118h+var_F0]
0x10043e6c0  mov     cs:qword_1004D3F70, rax
0x10043e6c7  mov     eax, ebx
0x10043e6c9  mov     r12, [rsp+118h+var_40]
0x10043e6d1  mov     rcx, [rsp+118h+var_58]
0x10043e6d9  xor     rcx, rsp; StackCookie
0x10043e6dc  call    __security_check_cookie
0x10043e6e1  add     rsp, 0E0h
0x10043e6e8  pop     r15
0x10043e6ea  pop     r14
0x10043e6ec  pop     r13
0x10043e6ee  pop     rdi
0x10043e6ef  pop     rsi
0x10043e6f0  pop     rbp
0x10043e6f1  pop     rbx
0x10043e6f2  retn
```
