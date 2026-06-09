# CImageGroup::CreateInitialize(CImageStore *,ushort const *)

- ea: `0x1800062a0`
- end: `0x180006382`
- name: `?CreateInitialize@CImageGroup@@QEAAJPEAVCImageStore@@PEBG@Z`
- size: `226`
- prototype: `__int64 __fastcall(CImageGroup *__hidden this, struct CImageStore *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800068e0`

## callees

- `0x1800062a0`
- `0x180006470`
- `0x180006714`
- `0x180006810`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000635e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000635e`
- `KERNEL32!CreateDirectoryW` at `0x180006302`
- `KERNEL32!CreateDirectoryW` at `0x180006302`
- `KERNEL32!GetLastError` at `0x180006312`
- `KERNEL32!GetLastError` at `0x180006312`
- `WdsCommonLib!ConcatenatePaths` at `0x1800062cd`
- `WdsCommonLib!ConcatenatePaths` at `0x1800062cd`

## pseudocode

```c
__int64 __fastcall CImageGroup::CreateInitialize(CImageGroup *this, struct CImageStore *a2, const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  signed int LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  LPCWSTR lpPathName; // [rsp+38h] [rbp+10h] BYREF

  lpPathName = 0;
  v6 = ConcatenatePaths(*((_QWORD *)a2 + 3), a3, &lpPathName);
  if ( (unsigned int)ElValidateWin32_0(v6, v7, v8, 63) )
  {
    if ( (int)v6 <= 0 )
      goto LABEL_11;
    v6 = (unsigned __int16)v6;
    goto LABEL_4;
  }
  if ( CreateDirectoryW(lpPathName, 0) )
  {
    v6 = CImageGroup::Initialize(this, a2, a3);
    ElValidateHr_1(v6, v10, v11, 87);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 183 )
    {
      v6 = -1056833015;
    }
    else if ( LastError > 0 )
    {
      v6 = (unsigned __int16)LastError;
LABEL_4:
      v6 |= 0x80070000;
    }
  }
LABEL_11:
  if ( lpPathName )
    operator delete((void *)lpPathName);
  return v6;
}

```

## disassembly

```asm
0x1800062a0  mov     rax, rsp
0x1800062a3  mov     [rax+8], rbx
0x1800062a7  mov     [rax+18h], rbp
0x1800062ab  mov     [rax+20h], rsi
0x1800062af  push    rdi
0x1800062b0  sub     rsp, 20h
0x1800062b4  and     qword ptr [rax+10h], 0
0x1800062b9  mov     rsi, rdx
0x1800062bc  mov     rdi, r8
0x1800062bf  mov     rbp, rcx
0x1800062c2  lea     r8, [rax+10h]
0x1800062c6  mov     rdx, rdi
0x1800062c9  mov     rcx, [rsi+18h]
0x1800062cd  call    cs:__imp_ConcatenatePaths
0x1800062d4  nop     dword ptr [rax+rax+00h]
0x1800062d9  mov     ecx, eax
0x1800062db  mov     r9d, 3Fh ; '?'
0x1800062e1  mov     ebx, eax
0x1800062e3  call    ElValidateWin32_0
0x1800062e8  test    eax, eax
0x1800062ea  jz      short loc_1800062FB
0x1800062ec  test    ebx, ebx
0x1800062ee  jle     short loc_180006354
0x1800062f0  movzx   ebx, bx
0x1800062f3  or      ebx, 80070000h
0x1800062f9  jmp     short loc_180006354
0x1800062fb  mov     rcx, [rsp+28h+lpPathName]; lpPathName
0x180006300  xor     edx, edx; lpSecurityAttributes
0x180006302  call    cs:__imp_CreateDirectoryW
0x180006309  nop     dword ptr [rax+rax+00h]
0x18000630e  test    eax, eax
0x180006310  jnz     short loc_180006337
0x180006312  call    cs:__imp_GetLastError
0x180006319  nop     dword ptr [rax+rax+00h]
0x18000631e  mov     ebx, eax
0x180006320  cmp     eax, 0B7h
0x180006325  jnz     short loc_18000632E
0x180006327  mov     ebx, 0C1020209h
0x18000632c  jmp     short loc_180006354
0x18000632e  test    eax, eax
0x180006330  jle     short loc_180006354
0x180006332  movzx   ebx, ax
0x180006335  jmp     short loc_1800062F3
0x180006337  mov     r8, rdi; unsigned __int16 *
0x18000633a  mov     rdx, rsi; struct CImageStore *
0x18000633d  mov     rcx, rbp; this
0x180006340  call    ?Initialize@CImageGroup@@QEAAJPEAVCImageStore@@PEBG@Z; CImageGroup::Initialize(CImageStore *,ushort const *)
0x180006345  mov     r9d, 57h ; 'W'
0x18000634b  mov     ecx, eax
0x18000634d  mov     ebx, eax
0x18000634f  call    ElValidateHr_1
0x180006354  mov     rcx, [rsp+28h+lpPathName]
0x180006359  test    rcx, rcx
0x18000635c  jz      short loc_18000636A
0x18000635e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006365  nop     dword ptr [rax+rax+00h]
0x18000636a  mov     rbp, [rsp+28h+arg_10]
0x18000636f  mov     eax, ebx
0x180006371  mov     rbx, [rsp+28h+arg_0]
0x180006376  mov     rsi, [rsp+28h+arg_18]
0x18000637b  add     rsp, 20h
0x18000637f  pop     rdi
0x180006380  retn
```
