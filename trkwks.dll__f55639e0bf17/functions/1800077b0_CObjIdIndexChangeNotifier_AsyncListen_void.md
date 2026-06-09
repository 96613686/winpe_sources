# CObjIdIndexChangeNotifier::AsyncListen(void)

- ea: `0x1800077b0`
- end: `0x180007a49`
- name: `?AsyncListen@CObjIdIndexChangeNotifier@@QEAAHXZ`
- size: `665`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000756c`

## callees

- `0x1800077b0`
- `0x180007b20`
- `0x18000d020`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001156b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001156b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800079c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800079c3`

## pseudocode

```c
__int64 __fastcall CObjIdIndexChangeNotifier::AsyncListen(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // ebx
  WCHAR *SpinCount; // r10
  __int64 v4; // rsi
  __int64 v5; // r9
  __int64 v6; // r8
  WCHAR *v7; // rcx
  __int64 v8; // rax
  WCHAR v9; // r11
  __int64 v10; // rcx
  WCHAR *v11; // rax
  int v12; // r8d
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  __int64 v16; // rax
  unsigned __int16 v17; // r9
  HANDLE FileW; // rax
  __int64 v20; // [rsp+50h] [rbp-298h]
  __int64 v21; // [rsp+A8h] [rbp-240h]
  WCHAR FileName[264]; // [rsp+B0h] [rbp-238h] BYREF

  HIWORD(v21) = HIWORD(this);
  v2 = 0;
  EnterCriticalSection(this + 1);
  if ( *(_QWORD *)&this->LockCount == -1 )
  {
    SpinCount = (WCHAR *)this->SpinCount;
    v4 = 2147483646;
    v5 = 2147483646;
    v6 = 260;
    v7 = FileName;
    v8 = 0;
    v2 = 1;
    while ( v6 )
    {
      if ( !v5 )
        goto LABEL_7;
      v9 = *SpinCount;
      if ( !*SpinCount )
        goto LABEL_7;
      ++SpinCount;
      *v7++ = v9;
      --v6;
      --v5;
      ++v8;
    }
    --v7;
LABEL_7:
    *v7 = 0;
    v10 = 260;
    v11 = FileName;
    v12 = 0;
    while ( v10 && *v11 )
    {
      ++v11;
      --v10;
    }
    if ( !v10 )
      v12 = -2147024809;
    if ( v12 < 0 )
      v20 = 0;
    else
      v20 = 260 - v10;
    if ( v12 >= 0 )
    {
      v13 = L"\\$Extend\\$ObjId:$O:$INDEX_ALLOCATION";
      v14 = 260 - v20;
      v15 = &FileName[v20];
      v16 = 0;
      while ( v14 )
      {
        if ( !v4 )
          goto LABEL_21;
        v17 = *v13;
        if ( !*v13 )
          goto LABEL_21;
        ++v13;
        *v15++ = v17;
        --v14;
        --v4;
        ++v16;
      }
      --v15;
LABEL_21:
      *v15 = 0;
    }
    FileW = CreateFileW(FileName, 1u, 7u, 0, 3u, 0x42000000u, 0);
    *(_QWORD *)&this->LockCount = FileW;
    if ( FileW == (HANDLE)-1LL )
      TrkRaiseLastError();
    CObjIdIndexChangeNotifier::StartListening((CObjIdIndexChangeNotifier *)this);
  }
  LeaveCriticalSection(this + 1);
  return v2;
}

```

## disassembly

```asm
0x1800077b0  mov     [rsp+arg_8], rbx
0x1800077b5  mov     [rsp+arg_10], rsi
0x1800077ba  push    rdi
0x1800077bb  push    r14
0x1800077bd  push    r15
0x1800077bf  sub     rsp, 2D0h
0x1800077c6  mov     rax, cs:__security_cookie
0x1800077cd  xor     rax, rsp
0x1800077d0  mov     [rsp+2E8h+var_28], rax
0x1800077d8  mov     rdi, rcx
0x1800077db  mov     [rsp+2E8h+var_240], rcx
0x1800077e3  xor     r15d, r15d
0x1800077e6  mov     ebx, r15d
0x1800077e9  add     rcx, 28h ; '('; lpCriticalSection
0x1800077ed  call    cs:__imp_EnterCriticalSection
0x1800077f3  nop
0x1800077f4  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800077f9  jnz     loc_180007A14
0x1800077ff  mov     r10, [rdi+20h]
0x180007803  mov     esi, 7FFFFFFEh
0x180007808  mov     r9d, esi
0x18000780b  mov     [rsp+2E8h+var_270], rsi
0x180007810  mov     [rsp+2E8h+var_280], r10
0x180007815  mov     edx, 104h
0x18000781a  mov     r8d, edx
0x18000781d  mov     [rsp+2E8h+var_278], rdx
0x180007822  lea     rcx, [rsp+2E8h+FileName]
0x18000782a  mov     [rsp+2E8h+var_2A8], rcx
0x18000782f  mov     eax, r15d
0x180007832  mov     [rsp+2E8h+var_2A0], rax
0x180007837  lea     ebx, [r15+1]
0x18000783b  test    r8, r8
0x18000783e  jz      loc_1800079DD
0x180007844  test    r9, r9
0x180007847  jz      short loc_180007883
0x180007849  movzx   r11d, word ptr [r10]
0x18000784d  test    r11w, r11w
0x180007851  jz      short loc_180007883
0x180007853  add     r10, 2
0x180007857  mov     [rsp+2E8h+var_280], r10
0x18000785c  mov     [rcx], r11w
0x180007860  add     rcx, 2
0x180007864  mov     [rsp+2E8h+var_2A8], rcx
0x180007869  sub     r8, rbx
0x18000786c  mov     [rsp+2E8h+var_278], r8
0x180007871  sub     r9, rbx
0x180007874  mov     [rsp+2E8h+var_270], r9
0x180007879  add     rax, rbx
0x18000787c  mov     [rsp+2E8h+var_2A0], rax
0x180007881  jmp     short loc_18000783B
0x180007883  test    r8, r8
0x180007886  jz      loc_1800079DD
0x18000788c  mov     [rcx], r15w
0x180007890  mov     [rsp+2E8h+var_298], r15
0x180007895  lea     r9, [rsp+2E8h+var_298]
0x18000789a  mov     rcx, rdx
0x18000789d  mov     [rsp+2E8h+var_260], rdx
0x1800078a5  lea     rax, [rsp+2E8h+FileName]
0x1800078ad  mov     [rsp+2E8h+var_268], rax
0x1800078b5  mov     r8d, r15d
0x1800078b8  test    rcx, rcx
0x1800078bb  jz      short loc_1800078DC
0x1800078bd  cmp     [rax], r15w
0x1800078c1  jz      short loc_1800078DC
0x1800078c3  add     rax, 2
0x1800078c7  mov     [rsp+2E8h+var_268], rax
0x1800078cf  sub     rcx, rbx
0x1800078d2  mov     [rsp+2E8h+var_260], rcx
0x1800078da  jmp     short loc_1800078B8
0x1800078dc  mov     eax, 80070057h
0x1800078e1  test    rcx, rcx
0x1800078e4  cmovz   r8d, eax
0x1800078e8  test    r8d, r8d
0x1800078eb  js      loc_1800079F3
0x1800078f1  mov     rax, rdx
0x1800078f4  sub     rax, rcx
0x1800078f7  mov     [r9], rax
0x1800078fa  test    r8d, r8d
0x1800078fd  js      loc_18000799D
0x180007903  mov     [rsp+2E8h+var_248], rsi
0x18000790b  lea     r8, aExtendObjidOIn; "\\$Extend\\$ObjId:$O:$INDEX_ALLOCATION"
0x180007912  mov     [rsp+2E8h+var_258], r8
0x18000791a  mov     rax, [rsp+2E8h+var_298]
0x18000791f  sub     rdx, rax
0x180007922  mov     [rsp+2E8h+var_250], rdx
0x18000792a  lea     rcx, [rsp+2E8h+FileName]
0x180007932  lea     rcx, [rcx+rax*2]
0x180007936  mov     [rsp+2E8h+var_290], rcx
0x18000793b  mov     rax, r15
0x18000793e  mov     [rsp+2E8h+var_288], rax
0x180007943  test    rdx, rdx
0x180007946  jz      loc_1800079FB
0x18000794c  test    rsi, rsi
0x18000794f  jz      short loc_180007994
0x180007951  movzx   r9d, word ptr [r8]
0x180007955  test    r9w, r9w
0x180007959  jz      short loc_180007994
0x18000795b  add     r8, 2
0x18000795f  mov     [rsp+2E8h+var_258], r8
0x180007967  mov     [rcx], r9w
0x18000796b  add     rcx, 2
0x18000796f  mov     [rsp+2E8h+var_290], rcx
0x180007974  sub     rdx, rbx
0x180007977  mov     [rsp+2E8h+var_250], rdx
0x18000797f  sub     rsi, rbx
0x180007982  mov     [rsp+2E8h+var_248], rsi
0x18000798a  add     rax, rbx
0x18000798d  mov     [rsp+2E8h+var_288], rax
0x180007992  jmp     short loc_180007943
0x180007994  test    rdx, rdx
0x180007997  jz      short loc_1800079FB
0x180007999  mov     [rcx], r15w
0x18000799d  mov     [rsp+2E8h+hTemplateFile], r15; hTemplateFile
0x1800079a2  mov     [rsp+2E8h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x1800079aa  mov     [rsp+2E8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800079b2  xor     r9d, r9d; lpSecurityAttributes
0x1800079b5  lea     r8d, [r9+7]; dwShareMode
0x1800079b9  mov     edx, ebx; dwDesiredAccess
0x1800079bb  lea     rcx, [rsp+2E8h+FileName]; lpFileName
0x1800079c3  call    cs:__imp_CreateFileW
0x1800079c9  mov     [rdi+8], rax
0x1800079cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800079d1  jz      short loc_180007A0E
0x1800079d3  mov     rcx, rdi; this
0x1800079d6  call    ?StartListening@CObjIdIndexChangeNotifier@@AEAAXXZ; CObjIdIndexChangeNotifier::StartListening(void)
0x1800079db  jmp     short loc_180007A14
0x1800079dd  sub     rcx, 2
0x1800079e1  mov     [rsp+2E8h+var_2A8], rcx
0x1800079e6  sub     rax, rbx
0x1800079e9  mov     [rsp+2E8h+var_2A0], rax
0x1800079ee  jmp     loc_18000788C
0x1800079f3  mov     [r9], r15
0x1800079f6  jmp     loc_1800078FA
0x1800079fb  sub     rcx, 2
0x1800079ff  mov     [rsp+2E8h+var_290], rcx
0x180007a04  sub     rax, rbx
0x180007a07  mov     [rsp+2E8h+var_288], rax
0x180007a0c  jmp     short loc_180007999
0x180007a0e  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180007a14  lea     rcx, [rdi+28h]; lpCriticalSection
0x180007a18  call    cs:__imp_LeaveCriticalSection
0x180007a1e  mov     eax, ebx
0x180007a20  mov     rcx, [rsp+2E8h+var_28]
0x180007a28  xor     rcx, rsp; StackCookie
0x180007a2b  call    __security_check_cookie
0x180007a30  lea     r11, [rsp+2E8h+var_18]
0x180007a38  mov     rbx, [r11+28h]
0x180007a3c  mov     rsi, [r11+30h]
0x180007a40  mov     rsp, r11
0x180007a43  pop     r15
0x180007a45  pop     r14
0x180007a47  pop     rdi
0x180007a48  retn
0x180011557  push    rbp
0x180011559  sub     rsp, 40h
0x18001155d  mov     rbp, rdx
0x180011560  mov     rcx, [rbp+0A8h]
0x180011567  add     rcx, 28h ; '('; lpCriticalSection
0x18001156b  call    cs:__imp_LeaveCriticalSection
0x180011571  nop
0x180011572  add     rsp, 40h
0x180011576  pop     rbp
0x180011577  retn
```
