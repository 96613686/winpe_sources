# CContact::Load(ushort const *,ulong)

- ea: `0x18007d7b0`
- end: `0x18007d9d8`
- name: `?Load@CContact@@UEAAJPEBGK@Z`
- size: `552`
- prototype: `__int64 __fastcall(CContact *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180002818`
- `0x180005d08`
- `0x180009aec`
- `0x18007d7b0`
- `0x18007e724`
- `0x18008f9fc`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `MSOERT2!OpenFileStreamShareW` at `0x18007d88e`
- `MSOERT2!OpenFileStreamShareW` at `0x18007d88e`
- `MSOERT2!HrCopyStream` at `0x18007d90a`
- `MSOERT2!HrCopyStream` at `0x18007d90a`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18007d8e7`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18007d8e7`
- `KERNEL32!GetFileAttributesExW` at `0x18007d8b0`
- `KERNEL32!GetFileAttributesExW` at `0x18007d8b0`
- `KERNEL32!GetCurrentThreadId` at `0x18007d7f8`
- `KERNEL32!GetCurrentThreadId` at `0x18007d7f8`

## pseudocode

```c
__int64 __fastcall CContact::Load(CContact *this, const unsigned __int16 *a2)
{
  int LastError; // ebx
  _DWORD *v5; // rsi
  const WCHAR *v6; // r14
  const WCHAR *v7; // rcx
  IStream *v8; // rax
  struct IStream *v9; // rsi
  int v10; // eax
  struct IStream *v12; // [rsp+30h] [rbp-40h] BYREF
  IStream *v13; // [rsp+38h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+40h] [rbp-30h] BYREF
  __int128 v15; // [rsp+50h] [rbp-20h]
  int v16; // [rsp+60h] [rbp-10h]

  v16 = 0;
  FileInformation = 0;
  v12 = 0;
  v15 = 0;
  v13 = 0;
  if ( GetCurrentThreadId() != *((_DWORD *)this + 172) )
  {
    LastError = -2147417842;
    goto LABEL_27;
  }
  if ( !a2 )
  {
    LastError = -2147024809;
    goto LABEL_27;
  }
  if ( *((_DWORD *)this + 12) )
  {
    LastError = -2147418113;
    goto LABEL_27;
  }
  v5 = (_DWORD *)((char *)this + 576);
  memset_0(*((void **)this + 73), 0, 2LL * *((unsigned int *)this + 144));
  *((_DWORD *)this + 144) = 0;
  LastError = STRW::Append((CContact *)((char *)this + 576), a2);
  if ( LastError >= 0 )
  {
    v6 = &Str;
    v7 = &Str;
    if ( *v5 )
      v7 = (const WCHAR *)*((_QWORD *)this + 73);
    v12 = 0;
    LastError = OpenFileStreamShareW(v7, 3, 0x80000000LL, 5, &v12);
    if ( LastError >= 0 )
    {
      if ( *v5 )
        v6 = (const WCHAR *)*((_QWORD *)this + 73);
      if ( !GetFileAttributesExW(v6, GetFileExInfoStandard, &FileInformation) )
      {
        LastError = HrGetLastError();
        goto LABEL_27;
      }
      *((_QWORD *)this + 76) = *(_QWORD *)((char *)&v15 + 4);
      if ( !*((_DWORD *)this + 163) )
      {
        LastError = CContact::_Load((CContact *)((char *)this - 56), v12);
        if ( LastError < 0 )
          goto LABEL_27;
        v10 = HashStreamMD5(v12, (struct _GUID *)((char *)this + 616));
        goto LABEL_25;
      }
      if ( !*((_DWORD *)this + 164) )
      {
        v9 = v12;
        goto LABEL_22;
      }
      v8 = SHCreateMemStream(0, 0);
      v13 = v8;
      v9 = v8;
      if ( !v8 )
      {
        LastError = -2147024882;
        goto LABEL_27;
      }
      LastError = HrCopyStream(v12, v8, 0);
      if ( LastError >= 0 )
      {
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v12);
        v12 = v9;
        v13 = 0;
LABEL_22:
        v10 = CContact::_Load((CContact *)((char *)this - 56), v9);
LABEL_25:
        LastError = v10;
        if ( v10 >= 0 )
          LastError = 0;
      }
    }
  }
LABEL_27:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v12);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13);
  if ( !*((_DWORD *)this + 12) )
  {
    memset_0(*((void **)this + 73), 0, 2LL * *((unsigned int *)this + 144));
    *((_DWORD *)this + 144) = 0;
    *((_QWORD *)this + 76) = 0;
    *(_OWORD *)((char *)this + 616) = 0;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18007d7b0  mov     [rsp-28h+arg_10], rbx
0x18007d7b5  mov     [rsp-28h+arg_18], rsi
0x18007d7ba  push    rbp
0x18007d7bb  push    rdi
0x18007d7bc  push    r12
0x18007d7be  push    r14
0x18007d7c0  push    r15
0x18007d7c2  mov     rbp, rsp
0x18007d7c5  sub     rsp, 70h
0x18007d7c9  mov     rax, cs:__security_cookie
0x18007d7d0  xor     rax, rsp
0x18007d7d3  mov     [rbp+var_8], rax
0x18007d7d7  xorps   xmm0, xmm0
0x18007d7da  xor     eax, eax
0x18007d7dc  xor     r12d, r12d
0x18007d7df  mov     [rbp+var_10], eax
0x18007d7e2  movups  [rbp+FileInformation], xmm0
0x18007d7e6  mov     [rbp+var_40], r12
0x18007d7ea  mov     rbx, rdx
0x18007d7ed  movups  [rbp+var_20], xmm0
0x18007d7f1  mov     [rbp+var_38], r12
0x18007d7f5  mov     rdi, rcx
0x18007d7f8  call    cs:__imp_GetCurrentThreadId
0x18007d7fe  cmp     eax, [rdi+2B0h]
0x18007d804  jz      short loc_18007D810
0x18007d806  mov     ebx, 8001010Eh
0x18007d80b  jmp     loc_18007D967
0x18007d810  test    rbx, rbx
0x18007d813  jnz     short loc_18007D81F
0x18007d815  mov     ebx, 80070057h
0x18007d81a  jmp     loc_18007D967
0x18007d81f  cmp     [rdi+30h], r12d
0x18007d823  jz      short loc_18007D82F
0x18007d825  mov     ebx, 8000FFFFh
0x18007d82a  jmp     loc_18007D967
0x18007d82f  lea     rsi, [rdi+240h]
0x18007d836  xor     edx, edx; Val
0x18007d838  mov     r8d, [rsi]
0x18007d83b  mov     rcx, [rsi+8]; void *
0x18007d83f  add     r8, r8; Size
0x18007d842  call    memset_0
0x18007d847  mov     rdx, rbx; unsigned __int16 *
0x18007d84a  mov     [rsi], r12d
0x18007d84d  mov     rcx, rsi; this
0x18007d850  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x18007d855  mov     ebx, eax
0x18007d857  test    eax, eax
0x18007d859  js      loc_18007D967
0x18007d85f  lea     r14, Str
0x18007d866  mov     rcx, r14
0x18007d869  cmp     [rsi], r12d
0x18007d86c  jz      short loc_18007D872
0x18007d86e  mov     rcx, [rsi+8]
0x18007d872  mov     edx, 3
0x18007d877  mov     [rbp+var_40], r12
0x18007d87b  lea     rax, [rbp+var_40]
0x18007d87f  mov     r8d, 80000000h
0x18007d885  mov     [rsp+70h+var_50], rax
0x18007d88a  lea     r9d, [rdx+2]
0x18007d88e  call    cs:__imp_OpenFileStreamShareW
0x18007d894  mov     ebx, eax
0x18007d896  test    eax, eax
0x18007d898  js      loc_18007D967
0x18007d89e  cmp     [rsi], r12d
0x18007d8a1  jz      short loc_18007D8A7
0x18007d8a3  mov     r14, [rsi+8]
0x18007d8a7  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18007d8ab  xor     edx, edx; fInfoLevelId
0x18007d8ad  mov     rcx, r14; lpFileName
0x18007d8b0  call    cs:__imp_GetFileAttributesExW
0x18007d8b6  test    eax, eax
0x18007d8b8  jnz     short loc_18007D8C6
0x18007d8ba  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18007d8bf  mov     ebx, eax
0x18007d8c1  jmp     loc_18007D967
0x18007d8c6  mov     rax, qword ptr [rbp+var_20+4]
0x18007d8ca  mov     [rdi+260h], rax
0x18007d8d1  cmp     [rdi+28Ch], r12d
0x18007d8d8  jz      short loc_18007D93B
0x18007d8da  cmp     [rdi+290h], r12d
0x18007d8e1  jz      short loc_18007D929
0x18007d8e3  xor     edx, edx; cbInit
0x18007d8e5  xor     ecx, ecx; pInit
0x18007d8e7  call    cs:__imp_SHCreateMemStream
0x18007d8ed  mov     [rbp+var_38], rax
0x18007d8f1  mov     rsi, rax
0x18007d8f4  test    rax, rax
0x18007d8f7  jnz     short loc_18007D900
0x18007d8f9  mov     ebx, 8007000Eh
0x18007d8fe  jmp     short loc_18007D967
0x18007d900  mov     rcx, [rbp+var_40]
0x18007d904  xor     r8d, r8d
0x18007d907  mov     rdx, rsi
0x18007d90a  call    cs:__imp_HrCopyStream
0x18007d910  mov     ebx, eax
0x18007d912  test    eax, eax
0x18007d914  js      short loc_18007D967
0x18007d916  lea     rcx, [rbp+var_40]
0x18007d91a  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007d91f  mov     [rbp+var_40], rsi
0x18007d923  mov     [rbp+var_38], r12
0x18007d927  jmp     short loc_18007D92D
0x18007d929  mov     rsi, [rbp+var_40]
0x18007d92d  mov     rdx, rsi; struct IStream *
0x18007d930  lea     rcx, [rdi-38h]; this
0x18007d934  call    ?_Load@CContact@@AEAAJPEAUIStream@@@Z; CContact::_Load(IStream *)
0x18007d939  jmp     short loc_18007D95E
0x18007d93b  mov     rdx, [rbp+var_40]; struct IStream *
0x18007d93f  lea     rcx, [rdi-38h]; this
0x18007d943  call    ?_Load@CContact@@AEAAJPEAUIStream@@@Z; CContact::_Load(IStream *)
0x18007d948  mov     ebx, eax
0x18007d94a  test    eax, eax
0x18007d94c  js      short loc_18007D967
0x18007d94e  mov     rcx, [rbp+var_40]; struct IStream *
0x18007d952  lea     rdx, [rdi+268h]; struct _GUID *
0x18007d959  call    ?HashStreamMD5@@YAJPEAUIStream@@PEAU_GUID@@@Z; HashStreamMD5(IStream *,_GUID *)
0x18007d95e  mov     ebx, eax
0x18007d960  test    eax, eax
0x18007d962  js      short loc_18007D967
0x18007d964  mov     ebx, r12d
0x18007d967  lea     rcx, [rbp+var_40]
0x18007d96b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007d970  lea     rcx, [rbp+var_38]
0x18007d974  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007d979  cmp     [rdi+30h], r12d
0x18007d97d  jnz     short loc_18007D9B1
0x18007d97f  mov     r8d, [rdi+240h]
0x18007d986  xor     edx, edx; Val
0x18007d988  mov     rcx, [rdi+248h]; void *
0x18007d98f  add     r8, r8; Size
0x18007d992  call    memset_0
0x18007d997  mov     [rdi+240h], r12d
0x18007d99e  xor     eax, eax
0x18007d9a0  xorps   xmm0, xmm0
0x18007d9a3  mov     [rdi+260h], rax
0x18007d9aa  movups  xmmword ptr [rdi+268h], xmm0
0x18007d9b1  mov     eax, ebx
0x18007d9b3  mov     rcx, [rbp+var_8]
0x18007d9b7  xor     rcx, rsp; StackCookie
0x18007d9ba  call    __security_check_cookie
0x18007d9bf  lea     r11, [rsp+70h+var_s0]
0x18007d9c4  mov     rbx, [r11+40h]
0x18007d9c8  mov     rsi, [r11+48h]
0x18007d9cc  mov     rsp, r11
0x18007d9cf  pop     r15
0x18007d9d1  pop     r14
0x18007d9d3  pop     r12
0x18007d9d5  pop     rdi
0x18007d9d6  pop     rbp
0x18007d9d7  retn
```
