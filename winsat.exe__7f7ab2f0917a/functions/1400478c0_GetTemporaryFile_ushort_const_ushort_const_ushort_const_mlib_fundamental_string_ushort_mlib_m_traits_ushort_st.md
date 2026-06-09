# GetTemporaryFile(ushort const *,ushort const *,ushort const *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400478c0`
- end: `0x140047b71`
- name: `?GetTemporaryFile@@YAKPEBG00AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x140013170`
- `0x140061600`
- `0x140079e98`

## callees

- `0x140005d78`
- `0x140005f10`
- `0x1400084b8`
- `0x140015bf4`
- `0x140016264`
- `0x140016480`
- `0x140016d04`
- `0x1400196bc`
- `0x140019a1c`
- `0x140019cb0`
- `0x1400478c0`
- `0x140047b78`
- `0x14005346c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140047b08`
- `KERNEL32!CreateFileW` at `0x140047b08`
- `KERNEL32!CloseHandle` at `0x140047b31`
- `KERNEL32!CloseHandle` at `0x140047b31`
- `KERNEL32!GetLastError` at `0x140047b14`
- `KERNEL32!GetLastError` at `0x140047b14`
- `msvcrt!modf` at `0x140047a42`
- `msvcrt!modf` at `0x140047a58`
- `msvcrt!modf` at `0x140047a42`
- `msvcrt!modf` at `0x140047a58`
- `USER32!CharLowerBuffW` at `0x140047920`
- `USER32!CharLowerBuffW` at `0x14004796c`
- `USER32!CharLowerBuffW` at `0x140047920`
- `USER32!CharLowerBuffW` at `0x14004796c`

## string_xrefs

- `0x140047acd`: `%s\TempWinSAT-%s-%s.%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetTemporaryFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD TemporaryPath; // ebx
  __int64 v9; // rbx
  _WORD *v10; // rbx
  __int64 v11; // rax
  double v12; // xmm7_8
  double v13; // xmm8_8
  HANDLE FileW; // rax
  int dwCreationDisposition; // [rsp+28h] [rbp-89h]
  int dwFlagsAndAttributes; // [rsp+30h] [rbp-81h]
  int hTemplateFile; // [rsp+38h] [rbp-79h]
  int v19; // [rsp+40h] [rbp-71h]
  int v20; // [rsp+48h] [rbp-69h]
  double v21; // [rsp+58h] [rbp-59h] BYREF
  __int64 v22; // [rsp+60h] [rbp-51h] BYREF
  __int64 v23; // [rsp+68h] [rbp-49h] BYREF
  double Y; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v25; // [rsp+78h] [rbp-39h] BYREF
  unsigned int v26; // [rsp+7Ch] [rbp-35h]
  __int64 v27; // [rsp+80h] [rbp-31h]
  __int64 v28; // [rsp+88h] [rbp-29h]
  __int64 v29; // [rsp+90h] [rbp-21h]
  int v30; // [rsp+98h] [rbp-19h]

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v22);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v23);
  TemporaryPath = GetTemporaryPath((__int64)&v22);
  if ( !TemporaryPath )
  {
    v9 = v22;
    CharLowerBuffW(*(LPWSTR *)(v22 + 24), *(_DWORD *)v22);
    if ( a3 )
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v21,
        a3);
      if ( **(_QWORD **)&v21 != 6
        || *(_WORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::at(
                       &v21,
                       5) != 58 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
        TemporaryPath = 1;
        goto LABEL_13;
      }
      CharLowerBuffW(*(LPWSTR *)(*(_QWORD *)&v21 + 24LL), **(_DWORD **)&v21);
      v10 = (_WORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::at(
                       &v21,
                       4);
      if ( *(_WORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::at(
                       &v22,
                       0) == *v10 )
      {
        v11 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::substr(
                &v22,
                &Y,
                2);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
          &v21,
          v11);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&Y);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
          &v22,
          *(_QWORD *)&v21);
      }
      else
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
          &v22,
          a3);
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
      v9 = v22;
    }
    v25 = 0;
    v26 = 12;
    v27 = 31;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    mlib::MDateTOD::set((mlib::MDateTOD *)&v25);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
      &v23,
      23);
    Y = 0.0;
    v12 = *(float *)&v29;
    v13 = modf(*(float *)&v29, &Y);
    v21 = 0.0;
    modf(v12, &v21);
    v20 = (int)(v13 * 1000.0);
    v19 = (int)v21;
    hTemplateFile = HIDWORD(v28);
    dwFlagsAndAttributes = v28;
    dwCreationDisposition = v27;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      &v23,
      L"%04d-%02d-%02d-%02d-%02d-%02d-%03d",
      v25,
      v26,
      dwCreationDisposition,
      dwFlagsAndAttributes,
      hTemplateFile,
      v19,
      v20);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
      a4,
      260);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      a4,
      L"%s\\TempWinSAT-%s-%s.%s",
      *(_QWORD *)(v9 + 24),
      a1,
      *(_QWORD *)(v23 + 24),
      a2);
    FileW = CreateFileW(*(LPCWSTR *)(*(_QWORD *)a4 + 24LL), 0xC0000000, 3u, 0, 1u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      TemporaryPath = GetLastError();
    }
    else
    {
      CloseHandle(FileW);
      TemporaryPath = 0;
    }
  }
LABEL_13:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
  return TemporaryPath;
}

```

## disassembly

```asm
0x1400478c0  mov     rax, rsp
0x1400478c3  push    rbp
0x1400478c4  push    rbx
0x1400478c5  push    rsi
0x1400478c6  push    rdi
0x1400478c7  push    r14
0x1400478c9  push    r15
0x1400478cb  lea     rbp, [rax-5Fh]
0x1400478cf  sub     rsp, 0D8h
0x1400478d6  movaps  xmmword ptr [rax-48h], xmm6
0x1400478da  movaps  xmmword ptr [rax-58h], xmm7
0x1400478de  movaps  xmmword ptr [rax-68h], xmm8
0x1400478e3  mov     rsi, r9
0x1400478e6  mov     rdi, r8
0x1400478e9  mov     r14, rdx
0x1400478ec  mov     r15, rcx
0x1400478ef  lea     rcx, [rbp+57h+var_A8]
0x1400478f3  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x1400478f8  nop
0x1400478f9  lea     rcx, [rbp+57h+var_A0]
0x1400478fd  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140047902  nop
0x140047903  lea     rcx, [rbp+57h+var_A8]
0x140047907  call    ?GetTemporaryPath@@YAKAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetTemporaryPath(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x14004790c  mov     ebx, eax
0x14004790e  test    eax, eax
0x140047910  jnz     loc_140047B39
0x140047916  mov     rbx, [rbp+57h+var_A8]
0x14004791a  mov     edx, [rbx]; cchLength
0x14004791c  mov     rcx, [rbx+18h]; lpsz
0x140047920  call    cs:__imp_CharLowerBuffW
0x140047926  test    rdi, rdi
0x140047929  jz      loc_1400479E7
0x14004792f  mov     rdx, rdi
0x140047932  lea     rcx, [rbp+57h+var_B0]
0x140047936  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14004793b  nop
0x14004793c  mov     rax, [rbp+57h+var_B0]
0x140047940  cmp     qword ptr [rax], 6
0x140047944  jnz     loc_140047B1E
0x14004794a  mov     edx, 5
0x14004794f  lea     rcx, [rbp+57h+var_B0]
0x140047953  call    ?at@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAG_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::at(unsigned __int64)
0x140047958  cmp     word ptr [rax], 3Ah ; ':'
0x14004795c  jnz     loc_140047B1E
0x140047962  mov     rcx, [rbp+57h+var_B0]
0x140047966  mov     edx, [rcx]; cchLength
0x140047968  mov     rcx, [rcx+18h]; lpsz
0x14004796c  call    cs:__imp_CharLowerBuffW
0x140047972  mov     edx, 4
0x140047977  lea     rcx, [rbp+57h+var_B0]
0x14004797b  call    ?at@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAG_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::at(unsigned __int64)
0x140047980  mov     rbx, rax
0x140047983  xor     edx, edx
0x140047985  lea     rcx, [rbp+57h+var_A8]
0x140047989  call    ?at@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAG_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::at(unsigned __int64)
0x14004798e  movzx   ecx, word ptr [rbx]
0x140047991  cmp     [rax], cx
0x140047994  lea     rcx, [rbp+57h+var_A8]
0x140047998  jnz     short loc_1400479D1
0x14004799a  or      r9, 0FFFFFFFFFFFFFFFFh
0x14004799e  lea     r8d, [r9+3]
0x1400479a2  lea     rdx, [rbp+57h+Y]
0x1400479a6  call    ?substr@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@_K0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::substr(unsigned __int64,unsigned __int64)
0x1400479ab  nop
0x1400479ac  mov     rdx, rax
0x1400479af  lea     rcx, [rbp+57h+var_B0]
0x1400479b3  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@AEBV12@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400479b8  nop
0x1400479b9  lea     rcx, [rbp+57h+Y]
0x1400479bd  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400479c2  mov     rdx, [rbp+57h+var_B0]
0x1400479c6  lea     rcx, [rbp+57h+var_A8]
0x1400479ca  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1400479cf  jmp     short loc_1400479DA
0x1400479d1  mov     rdx, rdi
0x1400479d4  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x1400479d9  nop
0x1400479da  lea     rcx, [rbp+57h+var_B0]
0x1400479de  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400479e3  mov     rbx, [rbp+57h+var_A8]
0x1400479e7  mov     [rbp+57h+var_90], 0
0x1400479ee  mov     [rbp+57h+var_8C], 0Ch
0x1400479f5  mov     [rbp+57h+var_88], 1Fh
0x1400479fd  mov     [rbp+57h+var_80], 0
0x140047a05  mov     [rbp+57h+var_78], 0
0x140047a0d  mov     [rbp+57h+var_70], 0
0x140047a14  lea     rcx, [rbp+57h+var_90]; this
0x140047a18  call    ?set@MDateTOD@mlib@@QEAAHXZ; mlib::MDateTOD::set(void)
0x140047a1d  mov     edx, 17h
0x140047a22  lea     rcx, [rbp+57h+var_A0]
0x140047a26  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x140047a2b  xorps   xmm6, xmm6
0x140047a2e  movsd   [rbp+57h+Y], xmm6
0x140047a33  movss   xmm7, dword ptr [rbp+57h+var_78]
0x140047a38  cvtps2pd xmm7, xmm7
0x140047a3b  lea     rdx, [rbp+57h+Y]; Y
0x140047a3f  movaps  xmm0, xmm7; X
0x140047a42  call    cs:__imp_modf
0x140047a48  movaps  xmm8, xmm0
0x140047a4c  movsd   [rbp+57h+var_B0], xmm6
0x140047a51  lea     rdx, [rbp+57h+var_B0]; Y
0x140047a55  movaps  xmm0, xmm7; X
0x140047a58  call    cs:__imp_modf
0x140047a5e  mulsd   xmm8, cs:__real@408f400000000000
0x140047a67  cvttsd2si rax, xmm8
0x140047a6c  cvttsd2si rcx, [rbp+57h+var_B0]
0x140047a72  mov     [rsp+100h+var_C0], eax
0x140047a76  mov     [rsp+100h+var_C8], ecx
0x140047a7a  mov     eax, dword ptr [rbp+57h+var_80+4]
0x140047a7d  mov     dword ptr [rsp+100h+hTemplateFile], eax
0x140047a81  mov     eax, dword ptr [rbp+57h+var_80]
0x140047a84  mov     [rsp+100h+dwFlagsAndAttributes], eax
0x140047a88  mov     eax, dword ptr [rbp+57h+var_88]
0x140047a8b  mov     [rsp+100h+dwCreationDisposition], eax
0x140047a8f  mov     r9d, [rbp+57h+var_8C]
0x140047a93  mov     r8d, [rbp+57h+var_90]
0x140047a97  lea     rdx, a04d02d02d02d02; "%04d-%02d-%02d-%02d-%02d-%02d-%03d"
0x140047a9e  lea     rcx, [rbp+57h+var_A0]
0x140047aa2  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140047aa7  mov     edx, 104h
0x140047aac  mov     rcx, rsi
0x140047aaf  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x140047ab4  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], r14
0x140047ab9  mov     rax, [rbp+57h+var_A0]
0x140047abd  mov     rcx, [rax+18h]
0x140047ac1  mov     qword ptr [rsp+100h+dwCreationDisposition], rcx
0x140047ac6  mov     r9, r15
0x140047ac9  mov     r8, [rbx+18h]
0x140047acd  lea     rdx, aSTempwinsatSSS; "%s\\TempWinSAT-%s-%s.%s"
0x140047ad4  mov     rcx, rsi
0x140047ad7  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140047adc  mov     rcx, [rsi]
0x140047adf  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x140047ae8  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140047af0  mov     [rsp+100h+dwCreationDisposition], 1; dwCreationDisposition
0x140047af8  xor     r9d, r9d; lpSecurityAttributes
0x140047afb  mov     edx, 0C0000000h; dwDesiredAccess
0x140047b00  lea     r8d, [r9+3]; dwShareMode
0x140047b04  mov     rcx, [rcx+18h]; lpFileName
0x140047b08  call    cs:__imp_CreateFileW
0x140047b0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140047b12  jnz     short loc_140047B2E
0x140047b14  call    cs:__imp_GetLastError
0x140047b1a  mov     ebx, eax
0x140047b1c  jmp     short loc_140047B39
0x140047b1e  lea     rcx, [rbp+57h+var_B0]
0x140047b22  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140047b27  mov     ebx, 1
0x140047b2c  jmp     short loc_140047B39
0x140047b2e  mov     rcx, rax; hObject
0x140047b31  call    cs:__imp_CloseHandle
0x140047b37  xor     ebx, ebx
0x140047b39  lea     rcx, [rbp+57h+var_A0]
0x140047b3d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140047b42  nop
0x140047b43  lea     rcx, [rbp+57h+var_A8]
0x140047b47  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140047b4c  mov     eax, ebx
0x140047b4e  lea     r11, [rsp+100h+var_28]
0x140047b56  movaps  xmm6, xmmword ptr [r11-18h]
0x140047b5b  movaps  xmm7, xmmword ptr [r11-28h]
0x140047b60  movaps  xmm8, xmmword ptr [r11-38h]
0x140047b65  mov     rsp, r11
0x140047b68  pop     r15
0x140047b6a  pop     r14
0x140047b6c  pop     rdi
0x140047b6d  pop     rsi
0x140047b6e  pop     rbx
0x140047b6f  pop     rbp
0x140047b70  retn
```
