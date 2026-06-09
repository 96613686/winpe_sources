# CUwfStaticVolumeConfiguration::IsFileExcluded(ushort const *,bool *)

- ea: `0x180008420`
- end: `0x180008514`
- name: `?IsFileExcluded@CUwfStaticVolumeConfiguration@@QEAAJPEBGPEA_N@Z`
- size: `244`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *this, wchar_t *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180016468`

## callees

- `0x180007700`
- `0x180008420`
- `0x18000e170`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800084d0`
- `msvcrt!_wcsnicmp` at `0x1800084d0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800084fb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800084fb`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::IsFileExcluded(
        CUwfStaticVolumeConfiguration *this,
        wchar_t *a2,
        bool *a3)
{
  struct _MULTISZ *v4; // rbx
  int FileExclusion; // ebp
  unsigned int v8; // esi
  const wchar_t *v9; // rcx
  size_t v10; // rdi
  unsigned __int64 v11; // r12
  struct _MULTISZ *v13; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  *a3 = 0;
  v13 = 0;
  FileExclusion = CUwfStaticVolumeConfiguration::FindFileExclusion(this, a2);
  if ( !FileExclusion )
  {
LABEL_18:
    *a3 = 1;
    goto LABEL_19;
  }
  FileExclusion = CUwfRegKey::QueryMultiSzValue(
                    (CUwfStaticVolumeConfiguration *)((char *)this + 16),
                    L"FileExceptionsUserDefined",
                    &v13);
  v4 = v13;
  if ( FileExclusion >= 0 )
  {
    v8 = 0;
    if ( *((_DWORD *)v13 + 6) )
    {
      do
      {
        v9 = *(const wchar_t **)(*((_QWORD *)v4 + 2) + 8LL * v8);
        if ( v9 && a2 )
        {
          v10 = -1;
          do
            ++v10;
          while ( v9[v10] );
          v11 = -1;
          do
            ++v11;
          while ( a2[v11] );
          if ( v10 && v9[v10 - 1] == 92 )
            --v10;
          if ( !_wcsnicmp(v9, a2, v10) && v11 > v10 && a2[v10] == 92 )
            goto LABEL_18;
        }
      }
      while ( ++v8 < *((_DWORD *)v4 + 6) );
    }
  }
LABEL_19:
  operator delete[](v4);
  return (unsigned int)FileExclusion;
}

```

## disassembly

```asm
0x180008420  mov     rax, rsp
0x180008423  push    rbx
0x180008424  push    rbp
0x180008425  push    rsi
0x180008426  push    rdi
0x180008427  push    r12
0x180008429  push    r13
0x18000842b  push    r14
0x18000842d  push    r15
0x18000842f  sub     rsp, 28h
0x180008433  xor     r13d, r13d
0x180008436  mov     r15, r8
0x180008439  mov     ebx, r13d
0x18000843c  mov     [r8], r13b
0x18000843f  mov     [rax+18h], rbx
0x180008443  mov     r14, rdx
0x180008446  mov     rdi, rcx
0x180008449  call    ?FindFileExclusion@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z; CUwfStaticVolumeConfiguration::FindFileExclusion(ushort const *)
0x18000844e  mov     ebp, eax
0x180008450  test    eax, eax
0x180008452  jz      loc_1800084F4
0x180008458  lea     rcx, [rdi+10h]; this
0x18000845c  lea     r8, [rsp+68h+arg_10]; struct _MULTISZ **
0x180008464  lea     rdx, Value; "FileExceptionsUserDefined"
0x18000846b  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x180008470  mov     ebp, eax
0x180008472  mov     rbx, [rsp+68h+arg_10]
0x18000847a  test    eax, eax
0x18000847c  js      short loc_1800084F8
0x18000847e  mov     esi, r13d
0x180008481  cmp     [rbx+18h], r13d
0x180008485  jbe     short loc_1800084F8
0x180008487  lea     edx, [r13+5Ch]
0x18000848b  mov     rax, [rbx+10h]
0x18000848f  mov     ecx, esi
0x180008491  mov     rcx, [rax+rcx*8]; String1
0x180008495  test    rcx, rcx
0x180008498  jz      short loc_1800084EB
0x18000849a  test    r14, r14
0x18000849d  jz      short loc_1800084EB
0x18000849f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800084a3  inc     rdi
0x1800084a6  cmp     [rcx+rdi*2], r13w
0x1800084ab  jnz     short loc_1800084A3
0x1800084ad  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800084b1  inc     r12
0x1800084b4  cmp     [r14+r12*2], r13w
0x1800084b9  jnz     short loc_1800084B1
0x1800084bb  test    rdi, rdi
0x1800084be  jz      short loc_1800084CA
0x1800084c0  cmp     dx, [rcx+rdi*2-2]
0x1800084c5  jnz     short loc_1800084CA
0x1800084c7  dec     rdi
0x1800084ca  mov     r8, rdi; MaxCount
0x1800084cd  mov     rdx, r14; String2
0x1800084d0  call    cs:__imp__wcsnicmp
0x1800084d6  mov     edx, 5Ch ; '\'
0x1800084db  test    eax, eax
0x1800084dd  jnz     short loc_1800084EB
0x1800084df  cmp     r12, rdi
0x1800084e2  jbe     short loc_1800084EB
0x1800084e4  cmp     dx, [r14+rdi*2]
0x1800084e9  jz      short loc_1800084F4
0x1800084eb  inc     esi
0x1800084ed  cmp     esi, [rbx+18h]
0x1800084f0  jb      short loc_18000848B
0x1800084f2  jmp     short loc_1800084F8
0x1800084f4  mov     byte ptr [r15], 1
0x1800084f8  mov     rcx, rbx
0x1800084fb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008501  mov     eax, ebp
0x180008503  add     rsp, 28h
0x180008507  pop     r15
0x180008509  pop     r14
0x18000850b  pop     r13
0x18000850d  pop     r12
0x18000850f  pop     rdi
0x180008510  pop     rsi
0x180008511  pop     rbp
0x180008512  pop     rbx
0x180008513  retn
```
