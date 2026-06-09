# mlib::FindFiles(ushort const *,ushort const *,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> &,unsigned __int64,bool)

- ea: `0x140041fac`
- end: `0x140042114`
- name: `?FindFiles@mlib@@YAKPEBG0AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@_K_N@Z`
- size: `360`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14004211c`
- `0x140049910`
- `0x14004c1dc`

## callees

- `0x140001abc`
- `0x140001ac8`
- `0x140041fac`
- `0x1400433f0`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x140042022`
- `KERNEL32!GetCurrentDirectoryW` at `0x140042022`
- `KERNEL32!GetLastError` at `0x14004202c`
- `KERNEL32!GetLastError` at `0x14004202c`
- `KERNEL32!SetLastError` at `0x14004200f`
- `KERNEL32!SetLastError` at `0x14004200f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::FindFiles(WCHAR *a1, __int64 a2, __int64 a3, __int64 a4)
{
  WCHAR *v7; // rdi
  WCHAR *v8; // rax
  DWORD LastError; // ebx
  void **v11; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v12; // [rsp+38h] [rbp-C8h]
  __int64 v13; // [rsp+240h] [rbp+140h]
  __int64 v14; // [rsp+248h] [rbp+148h]
  __int64 v15; // [rsp+250h] [rbp+150h]
  __int64 v16; // [rsp+258h] [rbp+158h]
  __int64 v17; // [rsp+260h] [rbp+160h]
  void **v18; // [rsp+268h] [rbp+168h]
  __int128 v19; // [rsp+270h] [rbp+170h]
  void *Block[2]; // [rsp+280h] [rbp+180h]
  __int64 v21; // [rsp+290h] [rbp+190h]

  if ( !a1 || (v7 = 0, !*a1) )
  {
    v8 = (WCHAR *)operator new[](0x208u);
    v7 = v8;
    if ( !v8 )
    {
      LastError = 8;
LABEL_5:
      SetLastError(LastError);
      return LastError;
    }
    if ( !GetCurrentDirectoryW(0x104u, v8) )
    {
      LastError = GetLastError();
      operator delete(v7);
      goto LABEL_5;
    }
    a1 = v7;
  }
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = -1;
  v17 = 0;
  v18 = &mlib::FSpecList<unsigned short>::`vftable';
  v19 = 0;
  *(_OWORD *)Block = 0;
  v12 = 0;
  v11 = &mlib::FileFinder<unsigned short>::`vftable';
  v21 = a3;
  LastError = mlib::TraverseDirT<unsigned short>::traverse_dir(&v11, a1, a2, a4);
  if ( v7 )
    operator delete(v7);
  v11 = &mlib::TraverseDirT<unsigned short>::`vftable';
  v18 = &mlib::FSpecList<unsigned short>::`vftable';
  operator delete(Block[1]);
  return LastError;
}

```

## disassembly

```asm
0x140041fac  mov     [rsp-8+arg_10], rbx
0x140041fb1  mov     [rsp-8+arg_18], rsi
0x140041fb6  push    rbp
0x140041fb7  push    rdi
0x140041fb8  push    r12
0x140041fba  push    r14
0x140041fbc  push    r15
0x140041fbe  lea     rbp, [rsp-1B0h]
0x140041fc6  sub     rsp, 2B0h
0x140041fcd  mov     rax, cs:__security_cookie
0x140041fd4  xor     rax, rsp
0x140041fd7  mov     [rbp+1D0h+var_30], rax
0x140041fde  mov     rbx, r9
0x140041fe1  mov     rsi, r8
0x140041fe4  mov     r14, rdx
0x140041fe7  xor     r15d, r15d
0x140041fea  test    rcx, rcx
0x140041fed  jz      short loc_140041FF8
0x140041fef  mov     edi, r15d
0x140041ff2  cmp     [rcx], r15w
0x140041ff6  jnz     short loc_140042041
0x140041ff8  mov     ecx, 208h; unsigned __int64
0x140041ffd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140042002  mov     rdi, rax
0x140042005  test    rax, rax
0x140042008  jnz     short loc_14004201A
0x14004200a  lea     ebx, [rax+8]
0x14004200d  mov     ecx, ebx; dwErrCode
0x14004200f  call    cs:__imp_SetLastError
0x140042015  jmp     loc_1400420E7
0x14004201a  mov     rdx, rdi; lpBuffer
0x14004201d  mov     ecx, 104h; nBufferLength
0x140042022  call    cs:__imp_GetCurrentDirectoryW
0x140042028  test    eax, eax
0x14004202a  jnz     short loc_14004203E
0x14004202c  call    cs:__imp_GetLastError
0x140042032  mov     ebx, eax
0x140042034  mov     rcx, rdi; Block
0x140042037  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004203c  jmp     short loc_14004200D
0x14004203e  mov     rcx, rdi
0x140042041  mov     [rbp+1D0h+var_90], r15
0x140042048  mov     [rbp+1D0h+var_88], r15
0x14004204f  mov     [rbp+1D0h+var_80], r15
0x140042056  mov     [rbp+1D0h+var_78], 0FFFFFFFFFFFFFFFFh
0x140042061  mov     [rbp+1D0h+var_70], r15
0x140042068  lea     r12, ??_7?$FSpecList@G@mlib@@6B@; const mlib::FSpecList<ushort>::`vftable'
0x14004206f  mov     [rbp+1D0h+var_68], r12
0x140042076  xorps   xmm0, xmm0
0x140042079  movdqa  [rbp+1D0h+var_60], xmm0
0x140042081  xorps   xmm1, xmm1
0x140042084  movdqa  xmmword ptr [rbp+1D0h+Block], xmm1
0x14004208c  mov     [rsp+2D0h+var_298], r15w
0x140042092  lea     rax, ??_7?$FileFinder@G@mlib@@6B@; const mlib::FileFinder<ushort>::`vftable'
0x140042099  mov     [rsp+2D0h+var_2A0], rax
0x14004209e  mov     [rbp+1D0h+var_40], rsi
0x1400420a5  mov     r9, rbx
0x1400420a8  mov     r8, r14
0x1400420ab  mov     rdx, rcx
0x1400420ae  lea     rcx, [rsp+2D0h+var_2A0]
0x1400420b3  call    ?traverse_dir@?$TraverseDirT@G@mlib@@QEAAKPEBG0_K_N@Z; mlib::TraverseDirT<ushort>::traverse_dir(ushort const *,ushort const *,unsigned __int64,bool)
0x1400420b8  mov     ebx, eax
0x1400420ba  test    rdi, rdi
0x1400420bd  jz      short loc_1400420C8
0x1400420bf  mov     rcx, rdi; Block
0x1400420c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400420c7  nop
0x1400420c8  lea     rax, ??_7?$TraverseDirT@G@mlib@@6B@; const mlib::TraverseDirT<ushort>::`vftable'
0x1400420cf  mov     [rsp+2D0h+var_2A0], rax
0x1400420d4  mov     [rbp+1D0h+var_68], r12
0x1400420db  mov     rcx, [rbp+1D0h+Block+8]; Block
0x1400420e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400420e7  mov     eax, ebx
0x1400420e9  mov     rcx, [rbp+1D0h+var_30]
0x1400420f0  xor     rcx, rsp; StackCookie
0x1400420f3  call    __security_check_cookie
0x1400420f8  lea     r11, [rsp+2D0h+var_20]
0x140042100  mov     rbx, [r11+40h]
0x140042104  mov     rsi, [r11+48h]
0x140042108  mov     rsp, r11
0x14004210b  pop     r15
0x14004210d  pop     r14
0x14004210f  pop     r12
0x140042111  pop     rdi
0x140042112  pop     rbp
0x140042113  retn
```
