# CWbemInstallObject::ExpandEnvironmentStringsW(ushort const *,ushort *,ulong)

- ea: `0x180042200`
- end: `0x1800423e1`
- name: `?ExpandEnvironmentStringsW@CWbemInstallObject@@SAKPEBGPEAGK@Z`
- size: `481`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18000a290`
- `0x180022e40`
- `0x1800298f0`
- `0x18002c98c`
- `0x18002ee7c`
- `0x180042200`
- `0x1800423f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800423c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800423c8`

## pseudocode

```c
__int64 __fastcall CWbemInstallObject::ExpandEnvironmentStringsW(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3)
{
  const unsigned __int16 *v5; // r15
  int v6; // ebx
  __int64 v7; // rdi
  int v8; // ebp
  _WORD *v9; // r12
  unsigned int v10; // r13d
  unsigned int v11; // eax
  void *v12; // rax
  const unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned int v16; // ebp
  unsigned __int64 v18; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int16 *v19[11]; // [rsp+30h] [rbp-58h] BYREF
  int pExceptionObject; // [rsp+A8h] [rbp+20h] BYREF

  v5 = a1;
  v6 = 0;
  pExceptionObject = 0;
  v18 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = 0;
  while ( (_DWORD)v7 )
  {
    if ( *v5 != 37 )
      goto LABEL_16;
    v9 = v5 + 1;
    v10 = 0;
    v11 = v7 - 1;
    if ( (_DWORD)v7 == 1 )
    {
LABEL_9:
      if ( v10 >= v11 )
        goto LABEL_16;
    }
    else
    {
      while ( *v9 != 37 )
      {
        ++v9;
        if ( ++v10 >= v11 )
          goto LABEL_9;
      }
    }
    v12 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v10 + 1, 2u));
    std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(v19, (__int64)v12);
    v13 = v19[0];
    if ( !v19[0] )
      throw (CX_MemoryException *)&pExceptionObject;
    StringCchCopyNW(v19[0], v10 + 1, v5 + 1, v10);
    v14 = a2;
    if ( !a3 )
      v14 = 0;
    v6 = CWbemInstallObject::ExpandVariableValue(v13, v14, a3, &v18);
    if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147024774 )
    {
      v15 = v18 - 1;
      v18 = v15;
      v8 += v15;
      v5 = v9 + 1;
      LODWORD(v7) = -2 - v10 + v7;
      if ( v6 < 0 )
      {
        pExceptionObject = v6;
      }
      else
      {
        v6 = pExceptionObject;
        if ( a3 < v15 )
        {
          a3 = 0;
          a2 = 0;
        }
        else
        {
          a3 -= v15;
          a2 += v15;
        }
      }
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)v19);
    }
    else
    {
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)v19);
      v6 = pExceptionObject;
LABEL_16:
      if ( v6 >= 0 )
      {
        if ( a3 <= 1 )
        {
          v6 = -2147024774;
          pExceptionObject = -2147024774;
        }
        else
        {
          --a3;
          *a2++ = *v5;
        }
      }
      ++v8;
      LODWORD(v7) = v7 - 1;
      ++v5;
    }
  }
  v16 = v8 + 1;
  if ( v6 >= 0 && a3 )
    *a2 = 0;
  else
    SetLastError(0x7Au);
  return v16;
}

```

## disassembly

```asm
0x180042200  push    rbx
0x180042202  push    rbp
0x180042203  push    rsi
0x180042204  push    rdi
0x180042205  push    r12
0x180042207  push    r13
0x180042209  push    r14
0x18004220b  push    r15
0x18004220d  sub     rsp, 48h
0x180042211  mov     esi, r8d
0x180042214  mov     r14, rdx
0x180042217  mov     r15, rcx
0x18004221a  xor     ecx, ecx
0x18004221c  mov     ebx, ecx
0x18004221e  mov     [rsp+88h+pExceptionObject], ecx
0x180042225  mov     [rsp+88h+var_60], rcx
0x18004222a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004222e  mov     rdi, r8
0x180042231  inc     rdi
0x180042234  cmp     [r15+rdi*2], cx
0x180042239  jnz     short loc_180042231
0x18004223b  mov     ebp, ecx
0x18004223d  cmp     edi, 1
0x180042240  jb      loc_1800423B3
0x180042246  cmp     word ptr [r15], 25h ; '%'
0x18004224b  jnz     loc_180042311
0x180042251  lea     r12, [r15+2]
0x180042255  mov     r13d, ecx
0x180042258  lea     eax, [rdi-1]
0x18004225b  test    eax, eax
0x18004225d  jz      short loc_180042273
0x18004225f  cmp     word ptr [r12], 25h ; '%'
0x180042265  jz      short loc_18004227C
0x180042267  add     r12, 2
0x18004226b  inc     r13d
0x18004226e  cmp     r13d, eax
0x180042271  jb      short loc_18004225F
0x180042273  cmp     r13d, eax
0x180042276  jnb     loc_180042311
0x18004227c  lea     ecx, [r13+1]
0x180042280  mov     [rsp+88h+var_68], rcx
0x180042285  mov     eax, 2
0x18004228a  mul     rcx
0x18004228d  cmovb   rax, r8
0x180042291  mov     rcx, rax; unsigned __int64
0x180042294  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180042299  mov     rdx, rax
0x18004229c  lea     rcx, [rsp+88h+var_58]
0x1800422a1  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x1800422a6  nop
0x1800422a7  mov     rbx, [rsp+88h+var_58]
0x1800422ac  test    rbx, rbx
0x1800422af  jz      loc_18004239E
0x1800422b5  mov     r9d, r13d; unsigned __int64
0x1800422b8  lea     r8, [r15+2]; unsigned __int16 *
0x1800422bc  mov     rdx, [rsp+88h+var_68]; unsigned __int64
0x1800422c1  mov     rcx, rbx; unsigned __int16 *
0x1800422c4  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800422c9  mov     r8d, esi; unsigned __int64
0x1800422cc  mov     rdx, r14
0x1800422cf  xor     eax, eax
0x1800422d1  test    esi, esi
0x1800422d3  cmovz   rdx, rax; unsigned __int16 *
0x1800422d7  lea     r9, [rsp+88h+var_60]; unsigned __int64 *
0x1800422dc  mov     rcx, rbx; unsigned __int16 *
0x1800422df  call    ?ExpandVariableValue@CWbemInstallObject@@CAJPEBGPEAG_KPEA_K@Z; CWbemInstallObject::ExpandVariableValue(ushort const *,ushort *,unsigned __int64,unsigned __int64 *)
0x1800422e4  mov     ebx, eax
0x1800422e6  mov     eax, 80000000h
0x1800422eb  lea     ecx, [rbx+rax]
0x1800422ee  test    eax, ecx
0x1800422f0  jnz     short loc_18004232A
0x1800422f2  cmp     ebx, 8007007Ah
0x1800422f8  jz      short loc_18004232A
0x1800422fa  lea     rcx, [rsp+88h+var_58]
0x1800422ff  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180042304  mov     ebx, [rsp+88h+pExceptionObject]
0x18004230b  xor     ecx, ecx
0x18004230d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042311  test    ebx, ebx
0x180042313  js      short loc_180042391
0x180042315  cmp     esi, 1
0x180042318  jbe     short loc_180042385
0x18004231a  dec     esi
0x18004231c  movzx   eax, word ptr [r15]
0x180042320  mov     [r14], ax
0x180042324  add     r14, 2
0x180042328  jmp     short loc_180042391
0x18004232a  mov     rcx, [rsp+88h+var_60]
0x18004232f  dec     rcx
0x180042332  mov     [rsp+88h+var_60], rcx
0x180042337  add     ebp, ecx
0x180042339  lea     r15, [r12+2]
0x18004233e  mov     eax, 0FFFFFFFEh
0x180042343  sub     eax, r13d
0x180042346  add     edi, eax
0x180042348  test    ebx, ebx
0x18004234a  js      short loc_180042369
0x18004234c  mov     eax, esi
0x18004234e  mov     ebx, [rsp+88h+pExceptionObject]
0x180042355  cmp     rax, rcx
0x180042358  jb      short loc_180042362
0x18004235a  sub     esi, ecx
0x18004235c  lea     r14, [r14+rcx*2]
0x180042360  jmp     short loc_180042370
0x180042362  xor     esi, esi
0x180042364  xor     r14d, r14d
0x180042367  jmp     short loc_180042370
0x180042369  mov     [rsp+88h+pExceptionObject], ebx
0x180042370  lea     rcx, [rsp+88h+var_58]
0x180042375  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18004237a  xor     ecx, ecx
0x18004237c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042380  jmp     loc_18004223D
0x180042385  mov     ebx, 8007007Ah
0x18004238a  mov     [rsp+88h+pExceptionObject], ebx
0x180042391  inc     ebp
0x180042393  dec     edi
0x180042395  add     r15, 2
0x180042399  jmp     loc_18004223D
0x18004239e  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800423a5  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800423ad  call    _CxxThrowException_0
0x1800423b3  inc     ebp
0x1800423b5  test    ebx, ebx
0x1800423b7  js      short loc_1800423C3
0x1800423b9  test    esi, esi
0x1800423bb  jz      short loc_1800423C3
0x1800423bd  mov     [r14], cx
0x1800423c1  jmp     short loc_1800423CE
0x1800423c3  mov     ecx, 7Ah ; 'z'; dwErrCode
0x1800423c8  call    cs:__imp_SetLastError
0x1800423ce  mov     eax, ebp
0x1800423d0  add     rsp, 48h
0x1800423d4  pop     r15
0x1800423d6  pop     r14
0x1800423d8  pop     r13
0x1800423da  pop     r12
0x1800423dc  pop     rdi
0x1800423dd  pop     rsi
0x1800423de  pop     rbp
0x1800423df  pop     rbx
0x1800423e0  retn
```
