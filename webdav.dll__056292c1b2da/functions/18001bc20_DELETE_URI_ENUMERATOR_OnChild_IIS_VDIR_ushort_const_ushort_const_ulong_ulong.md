# DELETE_URI_ENUMERATOR::OnChild(IIS_VDIR *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18001bc20`
- end: `0x18001bec2`
- name: `?OnChild@DELETE_URI_ENUMERATOR@@UEAAHPEAVIIS_VDIR@@PEBG1KK@Z`
- size: `674`
- prototype: `int(DELETE_URI_ENUMERATOR *__hidden this, struct IIS_VDIR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004474`
- `0x18001bc20`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001be0a`
- `msvcrt!_wcsnicmp` at `0x18001be0a`
- `msvcrt!_wcsicmp` at `0x18001bd17`
- `msvcrt!_wcsicmp` at `0x18001bd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd92`

## pseudocode

```c
__int64 __fastcall DELETE_URI_ENUMERATOR::OnChild(
        DELETE_URI_ENUMERATOR *this,
        struct IIS_VDIR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        char a6)
{
  const unsigned __int16 *v6; // rsi
  struct IIS_VDIR *v8; // r14
  signed int v10; // ebx
  STATIC_WSTRING_HASH *v12; // rsi
  __int64 v13; // r12
  __int64 v14; // rbx
  unsigned int i; // ecx
  struct STATIC_WSTRING_HASH_RECORD *Next; // rax
  __int64 *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // eax
  signed int LastError; // eax
  STATIC_WSTRING_HASH *v22; // r13
  unsigned int j; // ecx
  struct STATIC_WSTRING_HASH_RECORD *v24; // rax
  const wchar_t *v25; // rsi
  struct STATIC_WSTRING_HASH_RECORD *v27; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-39h]
  int v29; // [rsp+54h] [rbp-35h]
  struct IIS_VDIR *v30; // [rsp+58h] [rbp-31h]
  _OWORD v31[2]; // [rsp+60h] [rbp-29h] BYREF
  int v32; // [rsp+80h] [rbp-9h]

  v6 = a3;
  v30 = a2;
  v8 = a2;
  v10 = (***((__int64 (__fastcall ****)(_QWORD, const unsigned __int16 *, __int64))this + 2))(
          *((_QWORD *)this + 2),
          a3,
          2);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *))(**((_QWORD **)this + 2)
                                                                                                + 16LL))(
            *((_QWORD *)this + 2),
            v6,
            a4);
    if ( v10 >= 0 )
    {
      v12 = (STATIC_WSTRING_HASH *)*((_QWORD *)this + 3);
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( a4[v14] );
      v29 = 0;
      for ( i = 0; i < 0x83; ++i )
      {
        Next = (struct STATIC_WSTRING_HASH_RECORD *)*((_QWORD *)v12 + i);
        if ( Next )
          break;
      }
      v28 = i;
      v27 = Next;
      while ( Next )
      {
        if ( (_DWORD)v14 == *((_DWORD *)Next + 52) && !_wcsicmp(a4, *((const wchar_t **)Next + 24)) )
        {
          v10 = -2147024880;
          goto LABEL_36;
        }
        Next = STATIC_WSTRING_HASH::FindNext(v12, (struct STATIC_WSTRING_HASH_ITER *)&v27);
      }
      v17 = (__int64 *)*((_QWORD *)this + 4);
      v32 = 0;
      v18 = *v17;
      memset(v31, 0, sizeof(v31));
      if ( (*(unsigned int (__fastcall **)(__int64 *, const unsigned __int16 *, _QWORD, _OWORD *))(v18 + 88))(
             v17,
             a4,
             0,
             v31)
        && ((v19 = *v17, (v31[0] & 0x10) == 0)
          ? (v20 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(v19 + 104))(v17, a4))
          : (v20 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(v19 + 56))(v17, a4)),
            v20) )
      {
        v10 = 0;
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v10 == -2147024751 )
      {
        v22 = (STATIC_WSTRING_HASH *)*((_QWORD *)this + 3);
        do
          ++v13;
        while ( a4[v13] );
        v29 = 0;
        for ( j = 0; j < 0x83; ++j )
        {
          v24 = (struct STATIC_WSTRING_HASH_RECORD *)*((_QWORD *)v22 + j);
          if ( v24 )
            break;
        }
        v28 = j;
        v27 = v24;
        if ( v24 )
        {
          while ( 1 )
          {
            if ( (unsigned int)v13 < *((_DWORD *)v24 + 52) )
            {
              v25 = (const wchar_t *)*((_QWORD *)v24 + 24);
              if ( !_wcsnicmp(a4, v25, (unsigned int)v13) && v25[(unsigned int)v13] == 92 )
                break;
            }
            v24 = STATIC_WSTRING_HASH::FindNext(v22, (struct STATIC_WSTRING_HASH_ITER *)&v27);
            if ( !v24 )
              goto LABEL_35;
          }
          v10 = 0;
LABEL_35:
          v8 = v30;
        }
      }
LABEL_36:
      v6 = a3;
    }
    if ( *((_DWORD *)this + 10)
      && !*((_DWORD *)this + 11)
      && (v10 == -2147024891 || v10 == -2147024893 || v10 == -2147024773) )
    {
      *((_DWORD *)this + 2) = v10;
      return 0;
    }
    *((_DWORD *)this + 10) = 0;
    if ( (unsigned int)(v10 + 2147024894) <= 1 || v10 >= 0 )
      return 1;
  }
  else if ( (a6 & 0x10) != 0 )
  {
    return 1;
  }
  if ( *((_DWORD *)this + 11) )
    return 1;
  return (*(__int64 (__fastcall **)(DELETE_URI_ENUMERATOR *, struct IIS_VDIR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, signed int))(*(_QWORD *)this + 16LL))(
           this,
           v8,
           v6,
           a4,
           a5,
           v10);
}

```

## disassembly

```asm
0x18001bc20  push    rbp
0x18001bc22  push    rbx
0x18001bc23  push    rsi
0x18001bc24  push    rdi
0x18001bc25  push    r12
0x18001bc27  push    r13
0x18001bc29  push    r14
0x18001bc2b  push    r15
0x18001bc2d  lea     rbp, [rsp-0Fh]
0x18001bc32  sub     rsp, 98h
0x18001bc39  mov     rax, cs:__security_cookie
0x18001bc40  xor     rax, rsp
0x18001bc43  mov     [rbp+47h+var_48], rax
0x18001bc47  mov     rsi, r8
0x18001bc4a  mov     [rbp+47h+var_90], r8
0x18001bc4e  mov     rdi, rcx
0x18001bc51  mov     [rbp+47h+var_78], rdx
0x18001bc55  mov     rcx, [rcx+10h]
0x18001bc59  mov     r14, rdx
0x18001bc5c  mov     r8d, 2
0x18001bc62  mov     rdx, rsi
0x18001bc65  mov     r15, r9
0x18001bc68  mov     rax, [rcx]
0x18001bc6b  mov     rax, [rax]
0x18001bc6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc73  xor     r13d, r13d
0x18001bc76  mov     ebx, eax
0x18001bc78  test    eax, eax
0x18001bc7a  jns     short loc_18001BCAB
0x18001bc7c  test    byte ptr [rbp+47h+arg_28], 10h
0x18001bc80  jz      loc_18001BE8E
0x18001bc86  mov     eax, 1
0x18001bc8b  mov     rcx, [rbp+47h+var_48]
0x18001bc8f  xor     rcx, rsp; StackCookie
0x18001bc92  call    __security_check_cookie
0x18001bc97  add     rsp, 98h
0x18001bc9e  pop     r15
0x18001bca0  pop     r14
0x18001bca2  pop     r13
0x18001bca4  pop     r12
0x18001bca6  pop     rdi
0x18001bca7  pop     rsi
0x18001bca8  pop     rbx
0x18001bca9  pop     rbp
0x18001bcaa  retn
0x18001bcab  mov     rcx, [rdi+10h]
0x18001bcaf  mov     r8, r15
0x18001bcb2  mov     rdx, rsi
0x18001bcb5  mov     rax, [rcx]
0x18001bcb8  mov     rax, [rax+10h]
0x18001bcbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcc1  mov     ebx, eax
0x18001bcc3  test    eax, eax
0x18001bcc5  js      loc_18001BE38
0x18001bccb  mov     rsi, [rdi+18h]
0x18001bccf  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001bcd3  mov     rbx, r12
0x18001bcd6  inc     rbx
0x18001bcd9  cmp     [r15+rbx*2], r13w
0x18001bcde  jnz     short loc_18001BCD6
0x18001bce0  mov     [rbp+47h+var_7C], r13d
0x18001bce4  mov     ecx, r13d
0x18001bce7  mov     eax, ecx
0x18001bce9  mov     rax, [rsi+rax*8]
0x18001bced  test    rax, rax
0x18001bcf0  jnz     short loc_18001BCFC
0x18001bcf2  inc     ecx
0x18001bcf4  cmp     ecx, 83h
0x18001bcfa  jb      short loc_18001BCE7
0x18001bcfc  mov     [rbp+47h+var_80], ecx
0x18001bcff  mov     [rbp+47h+var_88], rax
0x18001bd03  jmp     short loc_18001BD2D
0x18001bd05  cmp     ebx, [rax+0D0h]
0x18001bd0b  jnz     short loc_18001BD21
0x18001bd0d  mov     rdx, [rax+0C0h]; String2
0x18001bd14  mov     rcx, r15; String1
0x18001bd17  call    cs:__imp__wcsicmp
0x18001bd1d  test    eax, eax
0x18001bd1f  jz      short loc_18001BD76
0x18001bd21  lea     rdx, [rbp+47h+var_88]; struct STATIC_WSTRING_HASH_ITER *
0x18001bd25  mov     rcx, rsi; this
0x18001bd28  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x18001bd2d  test    rax, rax
0x18001bd30  jnz     short loc_18001BD05
0x18001bd32  mov     rbx, [rdi+20h]
0x18001bd36  lea     r9, [rbp+47h+var_70]
0x18001bd3a  mov     [rbp+47h+var_50], eax
0x18001bd3d  xorps   xmm0, xmm0
0x18001bd40  xor     r8d, r8d
0x18001bd43  mov     rdx, r15
0x18001bd46  mov     rcx, rbx
0x18001bd49  mov     rax, [rbx]
0x18001bd4c  movups  [rbp+47h+var_70], xmm0
0x18001bd50  movups  [rbp+47h+var_60], xmm0
0x18001bd54  mov     rax, [rax+58h]
0x18001bd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd5d  test    eax, eax
0x18001bd5f  jz      short loc_18001BD92
0x18001bd61  test    byte ptr [rbp+47h+var_70], 10h
0x18001bd65  mov     rdx, r15
0x18001bd68  mov     rax, [rbx]
0x18001bd6b  mov     rcx, rbx
0x18001bd6e  jz      short loc_18001BD80
0x18001bd70  mov     rax, [rax+38h]
0x18001bd74  jmp     short loc_18001BD84
0x18001bd76  mov     ebx, 80070010h
0x18001bd7b  jmp     loc_18001BE34
0x18001bd80  mov     rax, [rax+68h]
0x18001bd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd89  test    eax, eax
0x18001bd8b  jz      short loc_18001BD92
0x18001bd8d  mov     ebx, r13d
0x18001bd90  jmp     short loc_18001BDA7
0x18001bd92  call    cs:__imp_GetLastError
0x18001bd98  mov     ebx, eax
0x18001bd9a  test    eax, eax
0x18001bd9c  jle     short loc_18001BDA7
0x18001bd9e  movzx   ebx, ax
0x18001bda1  or      ebx, 80070000h
0x18001bda7  cmp     ebx, 80070091h
0x18001bdad  jnz     loc_18001BE34
0x18001bdb3  mov     r13, [rdi+18h]
0x18001bdb7  xor     edx, edx
0x18001bdb9  inc     r12
0x18001bdbc  cmp     [r15+r12*2], dx
0x18001bdc1  jnz     short loc_18001BDB9
0x18001bdc3  mov     [rbp+47h+var_7C], edx
0x18001bdc6  mov     ecx, edx
0x18001bdc8  mov     eax, ecx
0x18001bdca  mov     rax, [r13+rax*8+0]
0x18001bdcf  test    rax, rax
0x18001bdd2  jnz     short loc_18001BDDE
0x18001bdd4  inc     ecx
0x18001bdd6  cmp     ecx, 83h
0x18001bddc  jb      short loc_18001BDC8
0x18001bdde  mov     [rbp+47h+var_80], ecx
0x18001bde1  mov     [rbp+47h+var_88], rax
0x18001bde5  test    rax, rax
0x18001bde8  jz      loc_18001BE6E
0x18001bdee  cmp     r12d, [rax+0D0h]
0x18001bdf5  jnb     short loc_18001BE1C
0x18001bdf7  mov     rsi, [rax+0C0h]
0x18001bdfe  mov     rcx, r15; String1
0x18001be01  mov     rdx, rsi; String2
0x18001be04  mov     r8d, r12d; MaxCount
0x18001be07  mov     r14d, r12d
0x18001be0a  call    cs:__imp__wcsnicmp
0x18001be10  test    eax, eax
0x18001be12  jnz     short loc_18001BE1C
0x18001be14  cmp     word ptr [rsi+r14*2], 5Ch ; '\'
0x18001be1a  jz      short loc_18001BE66
0x18001be1c  lea     rdx, [rbp+47h+var_88]; struct STATIC_WSTRING_HASH_ITER *
0x18001be20  mov     rcx, r13; this
0x18001be23  call    ?FindNext@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEAUSTATIC_WSTRING_HASH_ITER@@@Z; STATIC_WSTRING_HASH::FindNext(STATIC_WSTRING_HASH_ITER *)
0x18001be28  test    rax, rax
0x18001be2b  jnz     short loc_18001BDEE
0x18001be2d  xor     r13d, r13d
0x18001be30  mov     r14, [rbp+47h+var_78]
0x18001be34  mov     rsi, [rbp+47h+var_90]
0x18001be38  cmp     [rdi+28h], r13d
0x18001be3c  jz      short loc_18001BE73
0x18001be3e  cmp     [rdi+2Ch], r13d
0x18001be42  jnz     short loc_18001BE73
0x18001be44  cmp     ebx, 80070005h
0x18001be4a  jz      short loc_18001BE5C
0x18001be4c  cmp     ebx, 80070003h
0x18001be52  jz      short loc_18001BE5C
0x18001be54  cmp     ebx, 8007007Bh
0x18001be5a  jnz     short loc_18001BE73
0x18001be5c  mov     [rdi+8], ebx
0x18001be5f  xor     eax, eax
0x18001be61  jmp     loc_18001BC8B
0x18001be66  xor     r13d, r13d
0x18001be69  mov     ebx, r13d
0x18001be6c  jmp     short loc_18001BE30
0x18001be6e  xor     r13d, r13d
0x18001be71  jmp     short loc_18001BE34
0x18001be73  lea     eax, [rbx+7FF8FFFEh]
0x18001be79  mov     [rdi+28h], r13d
0x18001be7d  cmp     eax, 1
0x18001be80  jbe     loc_18001BC86
0x18001be86  test    ebx, ebx
0x18001be88  jns     loc_18001BC86
0x18001be8e  cmp     [rdi+2Ch], r13d
0x18001be92  jnz     loc_18001BC86
0x18001be98  mov     rax, [rdi]
0x18001be9b  mov     r9, r15
0x18001be9e  mov     r10d, [rbp+47h+arg_20]
0x18001bea2  mov     r8, rsi
0x18001bea5  mov     [rsp+0D0h+var_A8], ebx
0x18001bea9  mov     rdx, r14
0x18001beac  mov     rcx, rdi
0x18001beaf  mov     [rsp+0D0h+var_B0], r10d
0x18001beb4  mov     rax, [rax+10h]
0x18001beb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bebd  jmp     loc_18001BC8B
```
