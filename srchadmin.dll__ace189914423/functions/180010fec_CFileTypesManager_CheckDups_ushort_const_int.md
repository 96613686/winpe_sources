# CFileTypesManager::_CheckDups(ushort const *,int *)

- ea: `0x180010fec`
- end: `0x1800110c6`
- name: `?_CheckDups@CFileTypesManager@@AEAAJPEBGPEAH@Z`
- size: `218`
- prototype: `int(CFileTypesManager *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010d44`

## callees

- `0x18000687c`
- `0x180010fec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001108b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001108b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001101e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001105b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001101e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18001105b`

## pseudocode

```c
__int64 __fastcall CFileTypesManager::_CheckDups(HWND *this, const unsigned __int16 *a2, int *a3)
{
  unsigned int v6; // ebx
  int v7; // edi
  int v8; // esi
  _DWORD lParam[3]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v11[28]; // [rsp+3Ch] [rbp-8Ch] BYREF
  __int64 v12; // [rsp+58h] [rbp-70h]

  *a3 = -1;
  v6 = 0;
  v7 = 0;
  v8 = SendMessageW(*this, 0x1004u, 0, 0);
  while ( v7 < v8 )
  {
    lParam[0] = 4;
    lParam[1] = v7;
    lParam[2] = 0;
    memset_0(v11, 0, 0x4Cu);
    if ( !(unsigned int)SendMessageW(*this, 0x104Bu, 0, (LPARAM)lParam) )
      return (unsigned int)-2147467259;
    if ( !v12 )
      return (unsigned int)-2147467261;
    if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v12 + 64), -1, a2, -1) == 2 )
      goto LABEL_11;
    ++v7;
  }
  if ( v7 == v8 )
    return 1;
LABEL_11:
  *a3 = v7;
  return v6;
}

```

## disassembly

```asm
0x180010fec  push    rbx
0x180010fee  push    rbp
0x180010fef  push    rsi
0x180010ff0  push    rdi
0x180010ff1  push    r14
0x180010ff3  push    r15
0x180010ff5  sub     rsp, 98h
0x180010ffc  mov     r14, r8
0x180010fff  mov     dword ptr [r8], 0FFFFFFFFh
0x180011006  mov     rbp, rdx
0x180011009  mov     r15, rcx
0x18001100c  mov     rcx, [rcx]; hWnd
0x18001100f  xor     r8d, r8d; wParam
0x180011012  mov     edx, 1004h; Msg
0x180011017  xor     ebx, ebx
0x180011019  xor     edi, edi
0x18001101b  xor     r9d, r9d; lParam
0x18001101e  call    cs:__imp_SendMessageW
0x180011024  mov     rsi, rax
0x180011027  cmp     edi, esi
0x180011029  jge     short loc_1800110A8
0x18001102b  xor     edx, edx; Val
0x18001102d  mov     dword ptr [rsp+0C8h+lParam], 4
0x180011035  lea     rcx, [rsp+0C8h+var_8C]; void *
0x18001103a  mov     dword ptr [rsp+0C8h+lParam+4], edi
0x18001103e  mov     [rsp+0C8h+var_90], ebx
0x180011042  lea     r8d, [rdx+4Ch]; Size
0x180011046  call    memset_0
0x18001104b  mov     rcx, [r15]; hWnd
0x18001104e  lea     r9, [rsp+0C8h+lParam]; lParam
0x180011053  xor     r8d, r8d; wParam
0x180011056  mov     edx, 104Bh; Msg
0x18001105b  call    cs:__imp_SendMessageW
0x180011061  test    eax, eax
0x180011063  jz      short loc_1800110A1
0x180011065  mov     r8, [rsp+0C8h+var_70]
0x18001106a  test    r8, r8
0x18001106d  jz      short loc_18001109A
0x18001106f  mov     r8, [r8+40h]; lpString1
0x180011073  or      r9d, 0FFFFFFFFh; cchCount1
0x180011077  mov     [rsp+0C8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001107f  mov     [rsp+0C8h+lpString2], rbp; lpString2
0x180011084  lea     edx, [r9+2]; dwCmpFlags
0x180011088  lea     ecx, [rdx+7Eh]; Locale
0x18001108b  call    cs:__imp_CompareStringW
0x180011091  cmp     eax, 2
0x180011094  jz      short loc_1800110B1
0x180011096  inc     edi
0x180011098  jmp     short loc_180011027
0x18001109a  mov     ebx, 80004003h
0x18001109f  jmp     short loc_1800110B4
0x1800110a1  mov     ebx, 80004005h
0x1800110a6  jmp     short loc_1800110B4
0x1800110a8  jnz     short loc_1800110B1
0x1800110aa  mov     ebx, 1
0x1800110af  jmp     short loc_1800110B4
0x1800110b1  mov     [r14], edi
0x1800110b4  mov     eax, ebx
0x1800110b6  add     rsp, 98h
0x1800110bd  pop     r15
0x1800110bf  pop     r14
0x1800110c1  pop     rdi
0x1800110c2  pop     rsi
0x1800110c3  pop     rbp
0x1800110c4  pop     rbx
0x1800110c5  retn
```
