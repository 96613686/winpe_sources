# CProcessEntry::GetFileHandle(_EXTENSION_CONTROL_BLOCK *,ushort *,ulong,ulong)

- ea: `0x18001d530`
- end: `0x18001d71d`
- name: `?GetFileHandle@CProcessEntry@@AEAAPEAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAGKK@Z`
- size: `493`
- prototype: `__int64 __fastcall(CProcessEntry *this, struct _EXTENSION_CONTROL_BLOCK *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18001f364`

## callees

- `0x180012b30`
- `0x18001d530`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001d6a1`
- `KERNEL32!CreateFileW` at `0x18001d6a1`
- `ADVAPI32!SetThreadToken` at `0x18001d625`
- `ADVAPI32!SetThreadToken` at `0x18001d6d1`
- `ADVAPI32!SetThreadToken` at `0x18001d625`
- `ADVAPI32!SetThreadToken` at `0x18001d6d1`

## pseudocode

```c
__int64 __fastcall CProcessEntry::GetFileHandle(
        CProcessEntry *this,
        struct _EXTENSION_CONTROL_BLOCK *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v5; // r15d
  __int64 FileW; // r14
  DWORD v9; // esi
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  __int64 v12; // rax
  HANDLE v13; // r12
  HANDLE Token; // [rsp+80h] [rbp+18h] BYREF

  v5 = a5;
  Token = (HANDLE)-1LL;
  FileW = -1;
  v9 = -1073740630;
  if ( !a3 || a4 > 0x7FFFFFFFuLL )
    goto LABEL_27;
  v10 = a4;
  v11 = a3;
  if ( a4 )
  {
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
  }
  v12 = v10 ? a4 - v10 : 0LL;
  if ( !v10 )
    goto LABEL_27;
  if ( v12 + 1 != a4 )
    goto LABEL_19;
  if ( a5 == 49 )
  {
    if ( ((unsigned int (__fastcall *)(HCONN, __int64, HANDLE *, _QWORD, _QWORD))a2->ServerSupportFunction)(
           a2->ConnID,
           1011,
           &Token,
           0,
           0) )
    {
      v13 = Token;
      goto LABEL_17;
    }
LABEL_19:
    XspLogEvent(0xC00004AA);
    return FileW;
  }
  if ( a5 != 48 || *((_QWORD *)this + 1) == -1 )
    goto LABEL_19;
  v13 = (HANDLE)*((_QWORD *)this + 1);
LABEL_17:
  if ( !SetThreadToken(0, v13) )
  {
    GetLastWin32Error();
    goto LABEL_19;
  }
  FileW = (__int64)CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0x48000000u, 0);
  if ( FileW == -1 && (unsigned int)GetLastWin32Error() == -2147024891 )
    v9 = (v5 != 48) - 1073740628;
  if ( !SetThreadToken(0, 0) )
    GetLastWin32Error();
  if ( FileW == -1 )
  {
LABEL_27:
    if ( !a3 )
      return FileW;
    if ( v9 != -1073740630 )
    {
      XspLogEvent(v9);
      return FileW;
    }
    goto LABEL_19;
  }
  return FileW;
}

```

## disassembly

```asm
0x18001d530  mov     rax, rsp
0x18001d533  mov     [rax+8], rbx
0x18001d537  mov     [rax+10h], rbp
0x18001d53b  mov     [rax+20h], rsi
0x18001d53f  push    rdi
0x18001d540  push    r12
0x18001d542  push    r13
0x18001d544  push    r14
0x18001d546  push    r15
0x18001d548  sub     rsp, 40h
0x18001d54c  mov     r15d, [rsp+68h+arg_20]
0x18001d554  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001d558  mov     rbp, r8
0x18001d55b  mov     [rax+18h], r13
0x18001d55f  xor     ebx, ebx
0x18001d561  mov     r10d, r9d
0x18001d564  mov     r11, rdx
0x18001d567  mov     r8, rcx
0x18001d56a  mov     r14, r13
0x18001d56d  mov     r12, r13
0x18001d570  mov     esi, 0C00004AAh
0x18001d575  test    rbp, rbp
0x18001d578  jz      loc_18001D6ED
0x18001d57e  cmp     r10, 7FFFFFFFh
0x18001d585  ja      loc_18001D6ED
0x18001d58b  mov     ecx, r10d
0x18001d58e  mov     rax, rbp
0x18001d591  test    r9d, r9d
0x18001d594  jz      short loc_18001D5A5
0x18001d596  cmp     [rax], bx
0x18001d599  jz      short loc_18001D5A5
0x18001d59b  add     rax, 2
0x18001d59f  sub     rcx, 1
0x18001d5a3  jnz     short loc_18001D596
0x18001d5a5  mov     rax, rcx
0x18001d5a8  neg     rax
0x18001d5ab  sbb     edi, edi
0x18001d5ad  not     edi
0x18001d5af  and     edi, 80070057h
0x18001d5b5  test    rcx, rcx
0x18001d5b8  jz      short loc_18001D5C2
0x18001d5ba  mov     rax, r10
0x18001d5bd  sub     rax, rcx
0x18001d5c0  jmp     short loc_18001D5C5
0x18001d5c2  mov     rax, rbx
0x18001d5c5  test    rcx, rcx
0x18001d5c8  jz      loc_18001D6F2
0x18001d5ce  inc     rax
0x18001d5d1  cmp     rax, r10
0x18001d5d4  jnz     short loc_18001D636
0x18001d5d6  cmp     r15d, 31h ; '1'
0x18001d5da  jnz     short loc_18001D610
0x18001d5dc  mov     rcx, [r11+8]
0x18001d5e0  lea     r8, [rsp+68h+Token]
0x18001d5e8  mov     rax, [r11+0B8h]
0x18001d5ef  xor     r9d, r9d
0x18001d5f2  mov     edx, 3F3h
0x18001d5f7  mov     qword ptr [rsp+68h+dwCreationDisposition], rbx
0x18001d5fc  call    cs:__guard_dispatch_icall_fptr
0x18001d602  test    eax, eax
0x18001d604  jz      short loc_18001D636
0x18001d606  mov     r12, [rsp+68h+Token]
0x18001d60e  jmp     short loc_18001D620
0x18001d610  cmp     r15d, 30h ; '0'
0x18001d614  jnz     short loc_18001D636
0x18001d616  cmp     [r8+8], r13
0x18001d61a  jz      short loc_18001D636
0x18001d61c  mov     r12, [r8+8]
0x18001d620  mov     rdx, r12; Token
0x18001d623  xor     ecx, ecx; Thread
0x18001d625  call    cs:__imp_SetThreadToken
0x18001d62b  test    eax, eax
0x18001d62d  jnz     short loc_18001D67D
0x18001d62f  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001d634  mov     edi, eax
0x18001d636  cmp     r12, r13
0x18001d639  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x18001d63d  lea     r9d, [r15-30h]
0x18001d641  mov     r8, rbp
0x18001d644  setnz   bl
0x18001d647  lea     rdx, aSDD0x08x; "%s^%d^%d^0x%08x"
0x18001d64e  mov     ecx, 0C00004AAh; dwEventID
0x18001d653  mov     [rsp+68h+dwCreationDisposition], ebx
0x18001d657  call    XspLogEvent
0x18001d65c  lea     r11, [rsp+68h+var_28]
0x18001d661  mov     rax, r14
0x18001d664  mov     rbx, [r11+30h]
0x18001d668  mov     rbp, [r11+38h]
0x18001d66c  mov     rsi, [r11+48h]
0x18001d670  mov     rsp, r11
0x18001d673  pop     r15
0x18001d675  pop     r14
0x18001d677  pop     r13
0x18001d679  pop     r12
0x18001d67b  pop     rdi
0x18001d67c  retn
0x18001d67d  xor     r9d, r9d; lpSecurityAttributes
0x18001d680  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x18001d685  mov     [rsp+68h+dwFlagsAndAttributes], 48000000h; dwFlagsAndAttributes
0x18001d68d  mov     edx, 80000000h; dwDesiredAccess
0x18001d692  mov     rcx, rbp; lpFileName
0x18001d695  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18001d69d  lea     r8d, [r9+1]; dwShareMode
0x18001d6a1  call    cs:__imp_CreateFileW
0x18001d6a7  mov     r14, rax
0x18001d6aa  cmp     rax, r13
0x18001d6ad  jnz     short loc_18001D6CD
0x18001d6af  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001d6b4  mov     edi, eax
0x18001d6b6  cmp     eax, 80070005h
0x18001d6bb  jnz     short loc_18001D6CD
0x18001d6bd  cmp     r15d, 30h ; '0'
0x18001d6c1  mov     esi, ebx
0x18001d6c3  setnz   sil
0x18001d6c7  add     esi, 0C00004ACh
0x18001d6cd  xor     edx, edx; Token
0x18001d6cf  xor     ecx, ecx; Thread
0x18001d6d1  call    cs:__imp_SetThreadToken
0x18001d6d7  test    eax, eax
0x18001d6d9  jnz     short loc_18001D6E2
0x18001d6db  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001d6e0  mov     edi, eax
0x18001d6e2  cmp     r14, r13
0x18001d6e5  jnz     loc_18001D65C
0x18001d6eb  jmp     short loc_18001D6F2
0x18001d6ed  mov     edi, 80070057h
0x18001d6f2  test    rbp, rbp
0x18001d6f5  jz      loc_18001D65C
0x18001d6fb  cmp     esi, 0C00004AAh
0x18001d701  jz      loc_18001D636
0x18001d707  mov     r8, rbp
0x18001d70a  lea     rdx, aS; "%s"
0x18001d711  mov     ecx, esi; dwEventID
0x18001d713  call    XspLogEvent
0x18001d718  jmp     loc_18001D65C
```
