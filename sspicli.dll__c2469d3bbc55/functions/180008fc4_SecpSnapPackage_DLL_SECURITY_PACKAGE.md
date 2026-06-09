# SecpSnapPackage(_DLL_SECURITY_PACKAGE *)

- ea: `0x180008fc4`
- end: `0x1800090cb`
- name: `?SecpSnapPackage@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(struct _DLL_SECURITY_PACKAGE *)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ee0`
- `0x1800049c0`
- `0x180005400`
- `0x180005860`
- `0x1800061a0`
- `0x180007b58`
- `0x180009c90`

## callees

- `0x180008fc4`
- `0x180009744`
- `0x18001c99c`
- `0x18001d3ec`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009074`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009074`

## pseudocode

```c
__int64 __fastcall SecpSnapPackage(struct _DLL_SECURITY_PACKAGE *a1, __int64 a2, int a3)
{
  __int64 result; // rax
  __int64 v5; // rdi
  HMODULE Library; // rax
  unsigned int (__fastcall *v7)(struct _DLL_SECURITY_PACKAGE *); // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_QWORD *)(*((_QWORD *)a1 + 7) + 24LL),
      a3,
      *((_QWORD *)a1 + 3),
      *(_QWORD *)(*((_QWORD *)a1 + 7) + 24LL));
  if ( (*((_BYTE *)a1 + 16) & 1) != 0 )
    return SecSnapDelayLoadDll(a1);
  v5 = *((_QWORD *)a1 + 7);
  if ( *(_QWORD *)(v5 + 8) )
  {
    if ( (*((_BYTE *)a1 + 36) & 4) == 0 )
    {
      if ( (*((_BYTE *)a1 + 16) & 2) != 0 )
      {
        *((_QWORD *)a1 + 23) = *(_QWORD *)(v5 + 48) + 120LL * *((unsigned int *)a1 + 8);
        *((_QWORD *)a1 + 21) = &LsaFunctionTable;
        *((_QWORD *)a1 + 22) = &LsaFunctionTable;
        *((_QWORD *)a1 + 20) = LsaFunctionTableA;
        return 0;
      }
      return 2148074245LL;
    }
  }
  else
  {
    Library = LoadLibraryExW(*(LPCWSTR *)(v5 + 24), 0, 0);
    *(_QWORD *)(v5 + 8) = Library;
    if ( !Library )
      return 2148074245LL;
  }
  if ( (*((_BYTE *)a1 + 16) & 2) != 0 )
  {
    result = SecpSnapNewDll(a1);
    if ( (_DWORD)result )
      return result;
    v7 = (unsigned int (__fastcall *)(struct _DLL_SECURITY_PACKAGE *))*((_QWORD *)a1 + 24);
    if ( v7 && v7(a1) )
    {
      *((_DWORD *)a1 + 9) &= ~4u;
      return 0;
    }
  }
  else
  {
    *(_QWORD *)(v5 + 8) = 0;
  }
  return 2148074245LL;
}

```

## disassembly

```asm
0x180008fc4  mov     [rsp+arg_0], rbx
0x180008fc9  push    rdi
0x180008fca  sub     rsp, 30h
0x180008fce  mov     rbx, rcx
0x180008fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fd8  lea     rax, WPP_GLOBAL_Control
0x180008fdf  cmp     rcx, rax
0x180008fe2  jz      short loc_180009004
0x180008fe4  test    byte ptr [rcx+1Ch], 4
0x180008fe8  jz      short loc_180009004
0x180008fea  mov     rax, [rbx+38h]
0x180008fee  mov     r9, [rbx+18h]
0x180008ff2  mov     rcx, [rcx+10h]
0x180008ff6  mov     rdx, [rax+18h]
0x180008ffa  mov     [rsp+38h+var_18], rdx
0x180008fff  call    WPP_SF_PS
0x180009004  test    byte ptr [rbx+10h], 1
0x180009008  jz      short loc_180009017
0x18000900a  mov     rcx, rbx; struct _DLL_SECURITY_PACKAGE *
0x18000900d  call    ?SecSnapDelayLoadDll@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z; SecSnapDelayLoadDll(_DLL_SECURITY_PACKAGE *)
0x180009012  jmp     loc_1800090C0
0x180009017  mov     rdi, [rbx+38h]
0x18000901b  cmp     qword ptr [rdi+8], 0
0x180009020  jz      short loc_18000906B
0x180009022  test    byte ptr [rbx+24h], 4
0x180009026  jnz     short loc_180009083
0x180009028  test    byte ptr [rbx+10h], 2
0x18000902c  jz      loc_1800090BB
0x180009032  mov     eax, [rbx+20h]
0x180009035  imul    rcx, rax, 78h ; 'x'
0x180009039  lea     rax, LsaFunctionTableA
0x180009040  add     rcx, [rdi+30h]
0x180009044  mov     [rbx+0B8h], rcx
0x18000904b  lea     rcx, LsaFunctionTable
0x180009052  mov     [rbx+0A8h], rcx
0x180009059  mov     [rbx+0B0h], rcx
0x180009060  mov     [rbx+0A0h], rax
0x180009067  xor     eax, eax
0x180009069  jmp     short loc_1800090C0
0x18000906b  mov     rcx, [rdi+18h]; lpLibFileName
0x18000906f  xor     r8d, r8d; dwFlags
0x180009072  xor     edx, edx; hFile
0x180009074  call    cs:__imp_LoadLibraryExW
0x18000907a  mov     [rdi+8], rax
0x18000907e  test    rax, rax
0x180009081  jz      short loc_1800090BB
0x180009083  test    byte ptr [rbx+10h], 2
0x180009087  jz      short loc_1800090B3
0x180009089  mov     rcx, rbx; struct _DLL_SECURITY_PACKAGE *
0x18000908c  call    ?SecpSnapNewDll@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpSnapNewDll(_DLL_SECURITY_PACKAGE *)
0x180009091  test    eax, eax
0x180009093  jnz     short loc_1800090C0
0x180009095  mov     rax, [rbx+0C0h]
0x18000909c  test    rax, rax
0x18000909f  jz      short loc_1800090BB
0x1800090a1  mov     rcx, rbx
0x1800090a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a9  test    eax, eax
0x1800090ab  jz      short loc_1800090BB
0x1800090ad  and     dword ptr [rbx+24h], 0FFFFFFFBh
0x1800090b1  jmp     short loc_180009067
0x1800090b3  mov     qword ptr [rdi+8], 0
0x1800090bb  mov     eax, 80090305h
0x1800090c0  mov     rbx, [rsp+38h+arg_0]
0x1800090c5  add     rsp, 30h
0x1800090c9  pop     rdi
0x1800090ca  retn
```
