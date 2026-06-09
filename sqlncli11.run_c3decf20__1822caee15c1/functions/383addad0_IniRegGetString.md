# IniRegGetString

- ea: `0x383addad0`
- end: `0x383addc9a`
- name: `IniRegGetString`
- size: `458`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x383adcd50`

## callees

- `0x383add830`
- `0x383add980`
- `0x383addad0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x383addb90`
- `KERNEL32!CompareStringW` at `0x383addc48`
- `KERNEL32!CompareStringW` at `0x383addb90`
- `KERNEL32!CompareStringW` at `0x383addc48`
- `KERNEL32!HeapFree` at `0x383addbd7`
- `KERNEL32!HeapFree` at `0x383addc65`
- `KERNEL32!HeapFree` at `0x383addc8d`
- `KERNEL32!HeapFree` at `0x383addbd7`
- `KERNEL32!HeapFree` at `0x383addc65`
- `KERNEL32!HeapFree` at `0x383addc8d`
- `KERNEL32!GetProcessHeap` at `0x383addbc9`
- `KERNEL32!GetProcessHeap` at `0x383addc57`
- `KERNEL32!GetProcessHeap` at `0x383addc7f`
- `KERNEL32!GetProcessHeap` at `0x383addbc9`
- `KERNEL32!GetProcessHeap` at `0x383addc57`
- `KERNEL32!GetProcessHeap` at `0x383addc7f`

## pseudocode

```c
_WORD *__fastcall IniRegGetString(LPCWSTR lpAppName, PCNZWCH lpString2)
{
  _WORD *result; // rax
  _WORD *RawString; // rdi
  __int64 v6; // rbp
  __int64 v7; // rbx
  __int64 cchCount2; // rsi
  int v9; // r14d
  wchar_t **v10; // r15
  __int64 v11; // rbx
  HANDLE v12; // rax
  wchar_t **v13; // rbx
  const WCHAR *v14; // rax
  HANDLE v15; // rax
  HANDLE ProcessHeap; // rax

  result = (_WORD *)IniRegGetRawString(lpAppName, lpString2);
  RawString = result;
  if ( result && lpString2 && lpAppName )
  {
    if ( *result == 0xFFFF && !result[1] && dword_383B2BE04 )
    {
      v6 = -1;
      v7 = -1;
      do
        ++v7;
      while ( lpAppName[v7] );
      cchCount2 = -1;
      do
        ++cchCount2;
      while ( lpString2[cchCount2] );
      v9 = 0;
      v10 = &off_383B25CA8;
      while ( CompareStringW(0x400u, 1u, lpAppName, v7, *v10, *((_DWORD *)v10 + 2)) != 2 )
      {
        ++v9;
        v10 += 4;
        if ( v9 )
          goto LABEL_14;
      }
      v13 = &(&off_383B25CA8)[4 * v9];
      v14 = (const WCHAR *)IniExpandBuffer(v13[2]);
      if ( !v14 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, RawString);
        return 0;
      }
      do
        ++v6;
      while ( v14[v6] );
      if ( CompareStringW(0x400u, 1u, v14, v6, lpString2, cchCount2) == 2 )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, RawString);
        RawString = (_WORD *)IniRegGetRawString(lpAppName, v13[2]);
      }
    }
LABEL_14:
    if ( RawString && (*RawString != 0xFFFF || RawString[1]) )
    {
      v11 = IniExpandBuffer(RawString);
      v12 = GetProcessHeap();
      HeapFree(v12, 0, RawString);
      return (_WORD *)v11;
    }
    return RawString;
  }
  return result;
}

```

## disassembly

```asm
0x383addad0  push    rdi
0x383addad2  push    r12
0x383addad4  push    r13
0x383addad6  sub     rsp, 40h
0x383addada  mov     r13, rdx
0x383addadd  mov     r12, rcx
0x383addae0  call    IniRegGetRawString
0x383addae5  mov     rdi, rax
0x383addae8  test    rax, rax
0x383addaeb  jz      loc_383ADDBFC
0x383addaf1  test    r13, r13
0x383addaf4  jz      loc_383ADDBFC
0x383addafa  test    r12, r12
0x383addafd  jz      loc_383ADDBFC
0x383addb03  mov     [rsp+58h+arg_0], rbx
0x383addb08  mov     [rsp+58h+arg_8], rbp
0x383addb0d  mov     [rsp+58h+arg_10], rsi
0x383addb12  mov     eax, 0FFFFh
0x383addb17  mov     [rsp+58h+var_20], r14
0x383addb1c  mov     [rsp+58h+var_28], r15
0x383addb21  cmp     [rdi], ax
0x383addb24  jnz     loc_383ADDBAD
0x383addb2a  cmp     word ptr [rdi+2], 0
0x383addb2f  jnz     short loc_383ADDBAD
0x383addb31  cmp     cs:dword_383B2BE04, 0
0x383addb38  jz      short loc_383ADDBAD
0x383addb3a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x383addb3e  mov     rbx, rbp
0x383addb41  inc     rbx
0x383addb44  cmp     word ptr [r12+rbx*2], 0
0x383addb4a  jnz     short loc_383ADDB41
0x383addb4c  mov     rsi, rbp
0x383addb4f  nop
0x383addb50  inc     rsi
0x383addb53  cmp     word ptr [r13+rsi*2+0], 0
0x383addb5a  jnz     short loc_383ADDB50
0x383addb5c  xor     r14d, r14d
0x383addb5f  lea     r15, off_383B25CA8; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x383addb66  nop     word ptr [rax+rax+00000000h]
0x383addb70  mov     rcx, [r15]
0x383addb73  mov     eax, [r15+8]
0x383addb77  mov     r9d, ebx; cchCount1
0x383addb7a  mov     [rsp+58h+cchCount2], eax; cchCount2
0x383addb7e  mov     [rsp+58h+lpString2], rcx; lpString2
0x383addb83  mov     r8, r12; lpString1
0x383addb86  mov     ecx, 400h; Locale
0x383addb8b  mov     edx, 1; dwCmpFlags
0x383addb90  call    cs:__imp_CompareStringW
0x383addb96  cmp     eax, 2
0x383addb99  jz      short loc_383ADDC06
0x383addb9b  inc     r14d
0x383addb9e  add     r15, 20h ; ' '
0x383addba2  cmp     r14d, 1
0x383addba6  jb      short loc_383ADDB70
0x383addba8  mov     eax, 0FFFFh
0x383addbad  test    rdi, rdi
0x383addbb0  jz      short loc_383ADDBE0
0x383addbb2  cmp     [rdi], ax
0x383addbb5  jnz     short loc_383ADDBBE
0x383addbb7  cmp     word ptr [rdi+2], 0
0x383addbbc  jz      short loc_383ADDBE0
0x383addbbe  mov     rcx, rdi; lpSrc
0x383addbc1  call    IniExpandBuffer
0x383addbc6  mov     rbx, rax
0x383addbc9  call    cs:__imp_GetProcessHeap
0x383addbcf  mov     r8, rdi; lpMem
0x383addbd2  mov     rcx, rax; hHeap
0x383addbd5  xor     edx, edx; dwFlags
0x383addbd7  call    cs:__imp_HeapFree
0x383addbdd  mov     rdi, rbx
0x383addbe0  mov     r15, [rsp+58h+var_28]
0x383addbe5  mov     r14, [rsp+58h+var_20]
0x383addbea  mov     rsi, [rsp+58h+arg_10]
0x383addbef  mov     rbp, [rsp+58h+arg_8]
0x383addbf4  mov     rbx, [rsp+58h+arg_0]
0x383addbf9  mov     rax, rdi
0x383addbfc  add     rsp, 40h
0x383addc00  pop     r13
0x383addc02  pop     r12
0x383addc04  pop     rdi
0x383addc05  retn
0x383addc06  lea     rcx, off_383B25CA8; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x383addc0d  movsxd  rbx, r14d
0x383addc10  shl     rbx, 5
0x383addc14  add     rbx, rcx
0x383addc17  mov     rcx, [rbx+10h]; lpSrc
0x383addc1b  call    IniExpandBuffer
0x383addc20  test    rax, rax
0x383addc23  jz      short loc_383ADDC7F
0x383addc25  inc     rbp
0x383addc28  cmp     word ptr [rax+rbp*2], 0
0x383addc2d  jnz     short loc_383ADDC25
0x383addc2f  mov     r9d, ebp; cchCount1
0x383addc32  mov     r8, rax; lpString1
0x383addc35  mov     edx, 1; dwCmpFlags
0x383addc3a  mov     ecx, 400h; Locale
0x383addc3f  mov     [rsp+58h+cchCount2], esi; cchCount2
0x383addc43  mov     [rsp+58h+lpString2], r13; lpString2
0x383addc48  call    cs:__imp_CompareStringW
0x383addc4e  cmp     eax, 2
0x383addc51  jnz     loc_383ADDBA8
0x383addc57  call    cs:__imp_GetProcessHeap
0x383addc5d  mov     r8, rdi; lpMem
0x383addc60  xor     edx, edx; dwFlags
0x383addc62  mov     rcx, rax; hHeap
0x383addc65  call    cs:__imp_HeapFree
0x383addc6b  mov     rdx, [rbx+10h]; lpKeyName
0x383addc6f  mov     rcx, r12; lpAppName
0x383addc72  call    IniRegGetRawString
0x383addc77  mov     rdi, rax
0x383addc7a  jmp     loc_383ADDBA8
0x383addc7f  call    cs:__imp_GetProcessHeap
0x383addc85  mov     r8, rdi; lpMem
0x383addc88  xor     edx, edx; dwFlags
0x383addc8a  mov     rcx, rax; hHeap
0x383addc8d  call    cs:__imp_HeapFree
0x383addc93  xor     edi, edi
0x383addc95  jmp     loc_383ADDBE0
```
