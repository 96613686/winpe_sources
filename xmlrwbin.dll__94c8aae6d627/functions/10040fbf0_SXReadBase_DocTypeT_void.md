# SXReadBase::DocTypeT(void)

- ea: `0x10040fbf0`
- end: `0x10040ff5a`
- name: `?DocTypeT@SXReadBase@@IEAAXXZ`
- size: `874`
- prototype: `void __fastcall(SXReadBase *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10040edb0`

## callees

- `0x100401350`
- `0x100406be0`
- `0x10040fbf0`
- `0x100410e60`
- `0x100411000`
- `0x100411160`

## pseudocode

```c
void __fastcall SXReadBase::DocTypeT(SXReadBase *this)
{
  unsigned int Mb32; // eax
  unsigned int v3; // esi
  unsigned int v4; // edi
  unsigned int v5; // ecx
  unsigned __int8 *WCharBuffer; // rax
  __int64 v7; // rax
  _BYTE *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rdi
  unsigned int v11; // esi
  unsigned int v12; // eax
  unsigned __int8 *v13; // rax
  __int64 v14; // rax
  _BYTE *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rdi
  unsigned int v18; // esi
  unsigned int v19; // eax
  unsigned __int8 *v20; // rax
  __int64 v21; // rax
  _BYTE *v22; // rax
  unsigned int v23; // esi
  unsigned int v24; // edi
  unsigned int v25; // eax
  unsigned __int8 *v26; // rax

  if ( *((_DWORD *)this + 280) )
    goto LABEL_45;
  *((_DWORD *)this + 280) = 1;
  *((_QWORD *)this + 171) = &nullwstr;
  *((_DWORD *)this + 344) = 0;
  *((_DWORD *)this + 348) = 0;
  *((_DWORD *)this + 352) = 0;
  *((_QWORD *)this + 173) = &nullwstr;
  *((_QWORD *)this + 175) = &nullwstr;
  Mb32 = SXReadBase::GetMb32(this);
  v3 = Mb32;
  v4 = 2 * Mb32;
  if ( 2 * Mb32 < Mb32 )
    goto LABEL_47;
  v5 = *((_DWORD *)this + 174);
  if ( v5 && v4 > v5 )
    goto LABEL_46;
  _mm_lfence();
  if ( v4 )
  {
    WCharBuffer = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, 0, Mb32);
    *((_QWORD *)this + 169) = WCharBuffer;
    SXReadBase::GetBytes(this, WCharBuffer, v4);
  }
  else
  {
    *((_QWORD *)this + 169) = SXReadBase::GetWCharBuffer(this, 0, 2u);
  }
  v7 = *((_QWORD *)this + 179);
  *((_DWORD *)this + 340) = v3;
  if ( *((_QWORD *)this + 178) != v7 || (_mm_lfence(), SXReadBase::Pull(this)) )
  {
    _mm_lfence();
    v8 = (_BYTE *)*((_QWORD *)this + 178);
    if ( *v8 == 0xFB )
    {
      if ( v8 == *((_BYTE **)this + 179) )
      {
        _mm_lfence();
        if ( !SXReadBase::Pull(this) )
          goto LABEL_45;
      }
      ++*((_QWORD *)this + 178);
      _mm_lfence();
      v9 = SXReadBase::GetMb32(this);
      v10 = v9;
      v11 = 2 * v9;
      if ( 2 * v9 < v9 )
        goto LABEL_47;
      v12 = *((_DWORD *)this + 174);
      if ( v12 && v11 > v12 )
        goto LABEL_46;
      _mm_lfence();
      _mm_lfence();
      if ( v11 )
      {
        v13 = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, -1, v10);
        *((_QWORD *)this + 175) = v13;
        SXReadBase::GetBytes(this, v13, v11);
      }
      else
      {
        *((_QWORD *)this + 175) = SXReadBase::GetWCharBuffer(this, -1, 2u);
      }
      v14 = *((_QWORD *)this + 175);
      *((_DWORD *)this + 352) = v10;
      *(_WORD *)(v14 + 2 * v10) = 0;
    }
  }
  if ( *((_QWORD *)this + 178) != *((_QWORD *)this + 179) || (_mm_lfence(), SXReadBase::Pull(this)) )
  {
    _mm_lfence();
    v15 = (_BYTE *)*((_QWORD *)this + 178);
    if ( *v15 == 0xFA )
    {
      if ( v15 == *((_BYTE **)this + 179) )
      {
        _mm_lfence();
        if ( !SXReadBase::Pull(this) )
          goto LABEL_45;
      }
      ++*((_QWORD *)this + 178);
      _mm_lfence();
      v16 = SXReadBase::GetMb32(this);
      v17 = v16;
      v18 = 2 * v16;
      if ( 2 * v16 < v16 )
        goto LABEL_47;
      v19 = *((_DWORD *)this + 174);
      if ( v19 && v18 > v19 )
        goto LABEL_46;
      _mm_lfence();
      _mm_lfence();
      if ( v18 )
      {
        v20 = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, -1, v17);
        *((_QWORD *)this + 173) = v20;
        SXReadBase::GetBytes(this, v20, v18);
      }
      else
      {
        *((_QWORD *)this + 173) = SXReadBase::GetWCharBuffer(this, -1, 2u);
      }
      v21 = *((_QWORD *)this + 173);
      *((_DWORD *)this + 348) = v17;
      *(_WORD *)(v21 + 2 * v17) = 0;
    }
  }
  if ( *((_QWORD *)this + 178) != *((_QWORD *)this + 179) || (_mm_lfence(), SXReadBase::Pull(this)) )
  {
    _mm_lfence();
    v22 = (_BYTE *)*((_QWORD *)this + 178);
    if ( *v22 == 0xF9 )
    {
      if ( v22 != *((_BYTE **)this + 179) || (_mm_lfence(), SXReadBase::Pull(this)) )
      {
        ++*((_QWORD *)this + 178);
        _mm_lfence();
        v23 = SXReadBase::GetMb32(this);
        v24 = 2 * v23;
        if ( 2 * v23 >= v23 )
        {
          v25 = *((_DWORD *)this + 174);
          if ( !v25 || v24 <= v25 )
          {
            _mm_lfence();
            if ( v24 )
            {
              v26 = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, -1, v23);
              *((_QWORD *)this + 171) = v26;
              SXReadBase::GetBytes(this, v26, v24);
            }
            else
            {
              *((_QWORD *)this + 171) = SXReadBase::GetWCharBuffer(this, -1, 2u);
            }
            *((_DWORD *)this + 344) = v23;
            return;
          }
LABEL_46:
          MXRRaiseException(-1072897499);
          __debugbreak();
        }
LABEL_47:
        MXRRaiseException(-2147352566);
        JUMPOUT(0x10040FF59LL);
      }
LABEL_45:
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x10040fbf0  mov     [rsp+arg_0], rbx
0x10040fbf5  mov     [rsp+arg_8], rbp
0x10040fbfa  mov     [rsp+arg_10], rsi
0x10040fbff  push    rdi
0x10040fc00  sub     rsp, 20h
0x10040fc04  cmp     dword ptr [rcx+460h], 0
0x10040fc0b  mov     rbx, rcx
0x10040fc0e  jnz     loc_10040FF39
0x10040fc14  lea     rax, ?nullwstr@@3PA_WA; wchar_t near * nullwstr
0x10040fc1b  mov     dword ptr [rcx+460h], 1
0x10040fc25  xor     ebp, ebp
0x10040fc27  mov     [rcx+558h], rax
0x10040fc2e  mov     [rcx+560h], ebp
0x10040fc34  mov     [rcx+570h], ebp
0x10040fc3a  mov     [rcx+580h], ebp
0x10040fc40  mov     [rcx+568h], rax
0x10040fc47  mov     [rcx+578h], rax
0x10040fc4e  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040fc53  mov     esi, eax
0x10040fc55  lea     edi, [rax+rax]
0x10040fc58  cmp     edi, eax
0x10040fc5a  jb      loc_10040FF4F
0x10040fc60  mov     ecx, [rbx+2B8h]
0x10040fc66  test    ecx, ecx
0x10040fc68  jz      short loc_10040FC72
0x10040fc6a  cmp     edi, ecx
0x10040fc6c  ja      loc_10040FF44
0x10040fc72  lfence
0x10040fc75  xor     edx, edx; int
0x10040fc77  mov     rcx, rbx; this
0x10040fc7a  test    edi, edi
0x10040fc7c  jz      short loc_10040FC9D
0x10040fc7e  mov     r8d, esi; unsigned int
0x10040fc81  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fc86  mov     r8d, edi; unsigned int
0x10040fc89  mov     [rbx+548h], rax
0x10040fc90  mov     rdx, rax; unsigned __int8 *
0x10040fc93  mov     rcx, rbx; this
0x10040fc96  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040fc9b  jmp     short loc_10040FCAF
0x10040fc9d  mov     r8d, 2; unsigned int
0x10040fca3  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fca8  mov     [rbx+548h], rax
0x10040fcaf  mov     rax, [rbx+598h]
0x10040fcb6  mov     [rbx+550h], esi
0x10040fcbc  cmp     [rbx+590h], rax
0x10040fcc3  jnz     short loc_10040FCD8
0x10040fcc5  lfence
0x10040fcc8  mov     rcx, rbx; this
0x10040fccb  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fcd0  test    al, al
0x10040fcd2  jz      loc_10040FD8C
0x10040fcd8  lfence
0x10040fcdb  mov     rax, [rbx+590h]
0x10040fce2  cmp     byte ptr [rax], 0FBh
0x10040fce5  jnz     loc_10040FD8C
0x10040fceb  cmp     rax, [rbx+598h]
0x10040fcf2  jnz     short loc_10040FD07
0x10040fcf4  lfence
0x10040fcf7  mov     rcx, rbx; this
0x10040fcfa  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fcff  test    al, al
0x10040fd01  jz      loc_10040FF39
0x10040fd07  inc     qword ptr [rbx+590h]
0x10040fd0e  lfence
0x10040fd11  mov     rcx, rbx; this
0x10040fd14  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040fd19  mov     edi, eax
0x10040fd1b  lea     esi, [rdi+rdi]
0x10040fd1e  cmp     esi, eax
0x10040fd20  jb      loc_10040FF4F
0x10040fd26  mov     eax, [rbx+2B8h]
0x10040fd2c  test    eax, eax
0x10040fd2e  jz      short loc_10040FD38
0x10040fd30  cmp     esi, eax
0x10040fd32  ja      loc_10040FF44
0x10040fd38  lfence
0x10040fd3b  lfence
0x10040fd3e  mov     edx, 0FFFFFFFFh; int
0x10040fd43  mov     rcx, rbx; this
0x10040fd46  test    esi, esi
0x10040fd48  jz      short loc_10040FD69
0x10040fd4a  mov     r8d, edi; unsigned int
0x10040fd4d  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fd52  mov     r8d, esi; unsigned int
0x10040fd55  mov     [rbx+578h], rax
0x10040fd5c  mov     rdx, rax; unsigned __int8 *
0x10040fd5f  mov     rcx, rbx; this
0x10040fd62  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040fd67  jmp     short loc_10040FD7B
0x10040fd69  mov     r8d, 2; unsigned int
0x10040fd6f  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fd74  mov     [rbx+578h], rax
0x10040fd7b  mov     rax, [rbx+578h]
0x10040fd82  mov     [rbx+580h], edi
0x10040fd88  mov     [rax+rdi*2], bp
0x10040fd8c  mov     rax, [rbx+598h]
0x10040fd93  cmp     [rbx+590h], rax
0x10040fd9a  jnz     short loc_10040FDAF
0x10040fd9c  lfence
0x10040fd9f  mov     rcx, rbx; this
0x10040fda2  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fda7  test    al, al
0x10040fda9  jz      loc_10040FE63
0x10040fdaf  lfence
0x10040fdb2  mov     rax, [rbx+590h]
0x10040fdb9  cmp     byte ptr [rax], 0FAh
0x10040fdbc  jnz     loc_10040FE63
0x10040fdc2  cmp     rax, [rbx+598h]
0x10040fdc9  jnz     short loc_10040FDDE
0x10040fdcb  lfence
0x10040fdce  mov     rcx, rbx; this
0x10040fdd1  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fdd6  test    al, al
0x10040fdd8  jz      loc_10040FF39
0x10040fdde  inc     qword ptr [rbx+590h]
0x10040fde5  lfence
0x10040fde8  mov     rcx, rbx; this
0x10040fdeb  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040fdf0  mov     edi, eax
0x10040fdf2  lea     esi, [rdi+rdi]
0x10040fdf5  cmp     esi, eax
0x10040fdf7  jb      loc_10040FF4F
0x10040fdfd  mov     eax, [rbx+2B8h]
0x10040fe03  test    eax, eax
0x10040fe05  jz      short loc_10040FE0F
0x10040fe07  cmp     esi, eax
0x10040fe09  ja      loc_10040FF44
0x10040fe0f  lfence
0x10040fe12  lfence
0x10040fe15  mov     edx, 0FFFFFFFFh; int
0x10040fe1a  mov     rcx, rbx; this
0x10040fe1d  test    esi, esi
0x10040fe1f  jz      short loc_10040FE40
0x10040fe21  mov     r8d, edi; unsigned int
0x10040fe24  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fe29  mov     r8d, esi; unsigned int
0x10040fe2c  mov     [rbx+568h], rax
0x10040fe33  mov     rdx, rax; unsigned __int8 *
0x10040fe36  mov     rcx, rbx; this
0x10040fe39  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040fe3e  jmp     short loc_10040FE52
0x10040fe40  mov     r8d, 2; unsigned int
0x10040fe46  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fe4b  mov     [rbx+568h], rax
0x10040fe52  mov     rax, [rbx+568h]
0x10040fe59  mov     [rbx+570h], edi
0x10040fe5f  mov     [rax+rdi*2], bp
0x10040fe63  mov     rax, [rbx+598h]
0x10040fe6a  cmp     [rbx+590h], rax
0x10040fe71  jnz     short loc_10040FE86
0x10040fe73  lfence
0x10040fe76  mov     rcx, rbx; this
0x10040fe79  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fe7e  test    al, al
0x10040fe80  jz      loc_10040FF24
0x10040fe86  lfence
0x10040fe89  mov     rax, [rbx+590h]
0x10040fe90  cmp     byte ptr [rax], 0F9h
0x10040fe93  jnz     loc_10040FF24
0x10040fe99  cmp     rax, [rbx+598h]
0x10040fea0  jnz     short loc_10040FEB5
0x10040fea2  lfence
0x10040fea5  mov     rcx, rbx; this
0x10040fea8  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fead  test    al, al
0x10040feaf  jz      loc_10040FF39
0x10040feb5  inc     qword ptr [rbx+590h]
0x10040febc  lfence
0x10040febf  mov     rcx, rbx; this
0x10040fec2  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040fec7  mov     esi, eax
0x10040fec9  lea     edi, [rax+rax]
0x10040fecc  cmp     edi, eax
0x10040fece  jb      short loc_10040FF4F
0x10040fed0  mov     eax, [rbx+2B8h]
0x10040fed6  test    eax, eax
0x10040fed8  jz      short loc_10040FEDE
0x10040feda  cmp     edi, eax
0x10040fedc  ja      short loc_10040FF44
0x10040fede  lfence
0x10040fee1  mov     edx, 0FFFFFFFFh; int
0x10040fee6  mov     rcx, rbx; this
0x10040fee9  test    edi, edi
0x10040feeb  jz      short loc_10040FF0C
0x10040feed  mov     r8d, esi; unsigned int
0x10040fef0  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fef5  mov     r8d, edi; unsigned int
0x10040fef8  mov     [rbx+558h], rax
0x10040feff  mov     rdx, rax; unsigned __int8 *
0x10040ff02  mov     rcx, rbx; this
0x10040ff05  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040ff0a  jmp     short loc_10040FF1E
0x10040ff0c  mov     r8d, 2; unsigned int
0x10040ff12  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040ff17  mov     [rbx+558h], rax
0x10040ff1e  mov     [rbx+560h], esi
0x10040ff24  mov     rbx, [rsp+28h+arg_0]
0x10040ff29  mov     rbp, [rsp+28h+arg_8]
0x10040ff2e  mov     rsi, [rsp+28h+arg_10]
0x10040ff33  add     rsp, 20h
0x10040ff37  pop     rdi
0x10040ff38  retn
0x10040ff39  mov     ecx, 80004005h; int
0x10040ff3e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ff43  int     3; Trap to Debugger
0x10040ff44  mov     ecx, 0C00CE225h; int
0x10040ff49  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ff4e  int     3; Trap to Debugger
0x10040ff4f  mov     ecx, 8002000Ah; int
0x10040ff54  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
