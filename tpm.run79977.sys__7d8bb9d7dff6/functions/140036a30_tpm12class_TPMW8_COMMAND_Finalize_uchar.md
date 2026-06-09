# tpm12class::TPMW8_COMMAND::Finalize(uchar)

- ea: `0x140036a30`
- end: `0x140036c2d`
- name: `?Finalize@TPMW8_COMMAND@tpm12class@@MEAAJE@Z`
- size: `509`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400321dc`
- `0x140032300`
- `0x1400357dc`
- `0x140036534`
- `0x140036a30`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::Finalize(tpm12class::TPMW8_COMMAND *this, char a2)
{
  __int64 v3; // rdx
  int Parameter; // edi
  tpm12class::TPMW8_SESSION **v5; // rsi
  __int64 v6; // rdx
  tpm12class::TPMW8_SESSION *v7; // rcx
  tpm12class::TPMW8_SESSION *v8; // rcx
  unsigned int v9; // edx
  int v11; // edx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx

  if ( a2 )
  {
    if ( *((_WORD *)this + 28) != 0x8002 )
    {
LABEL_18:
      v9 = *((_DWORD *)this + 4);
      *((_DWORD *)this + 15) = v9;
      return (unsigned int)tpm12class::TpmDataObject::SetData(this, v9, 2u);
    }
    v3 = *((_QWORD *)this + 21);
    if ( !v3 || (*(_BYTE *)(v3 + 764) & 0x20) == 0 )
    {
      v5 = (tpm12class::TPMW8_SESSION **)((char *)this + 176);
      v6 = *((_QWORD *)this + 22);
      if ( v6 && (*(_BYTE *)(v6 + 764) & 0x20) != 0
        || (v6 = *((_QWORD *)this + 23)) != 0 && (*(_BYTE *)(v6 + 764) & 0x20) != 0 )
      {
        Parameter = tpm12class::TPMW8_COMMAND::EncryptFirstParameter(this, (tpm12class::TPMW8_AUTH_PROVIDER **)v6);
        if ( Parameter < 0 )
          return (unsigned int)Parameter;
      }
LABEL_12:
      v7 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
      if ( v7 )
      {
        Parameter = tpm12class::TPMW8_SESSION::Authenticate(v7, this);
        if ( Parameter < 0 )
          return (unsigned int)Parameter;
        if ( *v5 )
        {
          Parameter = tpm12class::TPMW8_SESSION::Authenticate(*v5, this);
          if ( Parameter < 0 )
            return (unsigned int)Parameter;
          v8 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 23);
          if ( v8 )
          {
            Parameter = tpm12class::TPMW8_SESSION::Authenticate(v8, this);
            if ( Parameter < 0 )
              return (unsigned int)Parameter;
          }
        }
      }
      goto LABEL_18;
    }
    Parameter = tpm12class::TPMW8_COMMAND::EncryptFirstParameter(this, (tpm12class::TPMW8_AUTH_PROVIDER **)v3);
    if ( Parameter >= 0 )
    {
      v5 = (tpm12class::TPMW8_SESSION **)((char *)this + 176);
      goto LABEL_12;
    }
  }
  else
  {
    Parameter = 0;
    if ( *((_WORD *)this + 29) == 0x8002 )
    {
      v11 = *((_DWORD *)this + 18);
      if ( *((_DWORD *)this + 6) != v11 + *((_DWORD *)this + 19) )
        return 2147942413LL;
      v13 = *((_QWORD *)this + 21);
      if ( v13 && (*(_BYTE *)(v13 + 764) & 0x40) != 0
        || (v14 = *((_QWORD *)this + 22)) != 0 && (*(_BYTE *)(v14 + 764) & 0x40) != 0
        || (v15 = *((_QWORD *)this + 23)) != 0 && (*(_BYTE *)(v15 + 764) & 0x40) != 0 )
      {
        if ( v11 )
        {
          v16 = *((_DWORD *)this + 20);
          if ( v16 )
          {
            if ( *((_WORD *)this + 72) )
              tpm12class::TpmDataObject::SetHashData(
                this,
                *((unsigned __int8 **)this + 19),
                *((unsigned __int16 *)this + 72),
                v16 + 2);
          }
        }
      }
      v17 = *((_QWORD *)this + 21);
      if ( v17 )
      {
        Parameter = (*(__int64 (__fastcall **)(__int64, tpm12class::TPMW8_COMMAND *))(*(_QWORD *)v17 + 8LL))(v17, this);
        if ( Parameter >= 0 )
        {
          v18 = *((_QWORD *)this + 22);
          if ( v18 )
          {
            Parameter = (*(__int64 (__fastcall **)(__int64, tpm12class::TPMW8_COMMAND *))(*(_QWORD *)v18 + 8LL))(
                          v18,
                          this);
            if ( Parameter >= 0 )
            {
              v19 = *((_QWORD *)this + 23);
              if ( v19 )
                return (unsigned int)(*(__int64 (__fastcall **)(__int64, tpm12class::TPMW8_COMMAND *))(*(_QWORD *)v19 + 8LL))(
                                       v19,
                                       this);
            }
          }
        }
      }
    }
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x140036a30  push    rbx
0x140036a32  push    rbp
0x140036a33  push    rsi
0x140036a34  push    rdi
0x140036a35  sub     rsp, 28h
0x140036a39  xor     ebp, ebp
0x140036a3b  mov     rbx, rcx
0x140036a3e  mov     eax, 8002h
0x140036a43  test    dl, dl
0x140036a45  jz      loc_140036B32
0x140036a4b  cmp     [rcx+38h], ax
0x140036a4f  jnz     loc_140036B19
0x140036a55  mov     rdx, [rcx+0A8h]; struct tpm12class::TPMW8_SESSION *
0x140036a5c  mov     cl, 20h ; ' '
0x140036a5e  test    rdx, rdx
0x140036a61  jz      short loc_140036A86
0x140036a63  test    [rdx+2FCh], cl
0x140036a69  jz      short loc_140036A86
0x140036a6b  mov     rcx, rbx; this
0x140036a6e  call    ?EncryptFirstParameter@TPMW8_COMMAND@tpm12class@@IEAAJPEAVTPMW8_SESSION@2@@Z; tpm12class::TPMW8_COMMAND::EncryptFirstParameter(tpm12class::TPMW8_SESSION *)
0x140036a73  mov     edi, eax
0x140036a75  test    eax, eax
0x140036a77  js      loc_140036C21
0x140036a7d  lea     rsi, [rbx+0B0h]
0x140036a84  jmp     short loc_140036AC3
0x140036a86  lea     rsi, [rbx+0B0h]
0x140036a8d  mov     rdx, [rsi]
0x140036a90  test    rdx, rdx
0x140036a93  jz      short loc_140036A9D
0x140036a95  test    [rdx+2FCh], cl
0x140036a9b  jnz     short loc_140036AB1
0x140036a9d  mov     rdx, [rbx+0B8h]; struct tpm12class::TPMW8_SESSION *
0x140036aa4  test    rdx, rdx
0x140036aa7  jz      short loc_140036AC3
0x140036aa9  test    [rdx+2FCh], cl
0x140036aaf  jz      short loc_140036AC3
0x140036ab1  mov     rcx, rbx; this
0x140036ab4  call    ?EncryptFirstParameter@TPMW8_COMMAND@tpm12class@@IEAAJPEAVTPMW8_SESSION@2@@Z; tpm12class::TPMW8_COMMAND::EncryptFirstParameter(tpm12class::TPMW8_SESSION *)
0x140036ab9  mov     edi, eax
0x140036abb  test    eax, eax
0x140036abd  js      loc_140036C21
0x140036ac3  mov     rcx, [rbx+0A8h]; this
0x140036aca  test    rcx, rcx
0x140036acd  jz      short loc_140036B19
0x140036acf  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x140036ad2  call    ?Authenticate@TPMW8_SESSION@tpm12class@@QEAAJPEAVTpmDataObject@2@@Z; tpm12class::TPMW8_SESSION::Authenticate(tpm12class::TpmDataObject *)
0x140036ad7  mov     edi, eax
0x140036ad9  test    eax, eax
0x140036adb  js      loc_140036C21
0x140036ae1  mov     rcx, [rsi]; this
0x140036ae4  test    rcx, rcx
0x140036ae7  jz      short loc_140036B19
0x140036ae9  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x140036aec  call    ?Authenticate@TPMW8_SESSION@tpm12class@@QEAAJPEAVTpmDataObject@2@@Z; tpm12class::TPMW8_SESSION::Authenticate(tpm12class::TpmDataObject *)
0x140036af1  mov     edi, eax
0x140036af3  test    eax, eax
0x140036af5  js      loc_140036C21
0x140036afb  mov     rcx, [rbx+0B8h]; this
0x140036b02  test    rcx, rcx
0x140036b05  jz      short loc_140036B19
0x140036b07  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x140036b0a  call    ?Authenticate@TPMW8_SESSION@tpm12class@@QEAAJPEAVTpmDataObject@2@@Z; tpm12class::TPMW8_SESSION::Authenticate(tpm12class::TpmDataObject *)
0x140036b0f  mov     edi, eax
0x140036b11  test    eax, eax
0x140036b13  js      loc_140036C21
0x140036b19  mov     edx, [rbx+10h]; unsigned int
0x140036b1c  mov     r8d, 2; unsigned int
0x140036b22  mov     rcx, rbx; this
0x140036b25  mov     [rbx+3Ch], edx
0x140036b28  call    ?SetData@TpmDataObject@tpm12class@@QEAAJII@Z; tpm12class::TpmDataObject::SetData(uint,uint)
0x140036b2d  jmp     loc_140036C1F
0x140036b32  mov     edi, ebp
0x140036b34  cmp     [rcx+3Ah], ax
0x140036b38  jnz     loc_140036C21
0x140036b3e  mov     edx, [rcx+48h]
0x140036b41  mov     ecx, [rcx+4Ch]
0x140036b44  add     ecx, edx
0x140036b46  cmp     [rbx+18h], ecx
0x140036b49  jz      short loc_140036B55
0x140036b4b  mov     eax, 8007000Dh
0x140036b50  jmp     loc_140036C23
0x140036b55  mov     rax, [rbx+0A8h]
0x140036b5c  mov     cl, 40h ; '@'
0x140036b5e  test    rax, rax
0x140036b61  jz      short loc_140036B6B
0x140036b63  test    [rax+2FCh], cl
0x140036b69  jnz     short loc_140036B93
0x140036b6b  mov     rax, [rbx+0B0h]
0x140036b72  test    rax, rax
0x140036b75  jz      short loc_140036B7F
0x140036b77  test    [rax+2FCh], cl
0x140036b7d  jnz     short loc_140036B93
0x140036b7f  mov     rax, [rbx+0B8h]
0x140036b86  test    rax, rax
0x140036b89  jz      short loc_140036BC2
0x140036b8b  test    [rax+2FCh], cl
0x140036b91  jz      short loc_140036BC2
0x140036b93  test    edx, edx
0x140036b95  jz      short loc_140036BC2
0x140036b97  mov     r9d, [rbx+50h]
0x140036b9b  test    r9d, r9d
0x140036b9e  jz      short loc_140036BC2
0x140036ba0  movzx   eax, word ptr [rbx+90h]
0x140036ba7  test    ax, ax
0x140036baa  jz      short loc_140036BC2
0x140036bac  mov     rdx, [rbx+98h]; unsigned __int8 *
0x140036bb3  add     r9d, 2; unsigned int
0x140036bb7  mov     r8d, eax; unsigned int
0x140036bba  mov     rcx, rbx; this
0x140036bbd  call    ?SetHashData@TpmDataObject@tpm12class@@QEAAJPEAEII@Z; tpm12class::TpmDataObject::SetHashData(uchar *,uint,uint)
0x140036bc2  mov     rcx, [rbx+0A8h]
0x140036bc9  test    rcx, rcx
0x140036bcc  jz      short loc_140036C21
0x140036bce  mov     rax, [rcx]
0x140036bd1  mov     rdx, rbx
0x140036bd4  mov     rax, [rax+8]
0x140036bd8  call    _guard_dispatch_icall
0x140036bdd  mov     edi, eax
0x140036bdf  test    eax, eax
0x140036be1  js      short loc_140036C21
0x140036be3  mov     rcx, [rbx+0B0h]
0x140036bea  test    rcx, rcx
0x140036bed  jz      short loc_140036C21
0x140036bef  mov     rax, [rcx]
0x140036bf2  mov     rdx, rbx
0x140036bf5  mov     rax, [rax+8]
0x140036bf9  call    _guard_dispatch_icall
0x140036bfe  mov     edi, eax
0x140036c00  test    eax, eax
0x140036c02  js      short loc_140036C21
0x140036c04  mov     rcx, [rbx+0B8h]
0x140036c0b  test    rcx, rcx
0x140036c0e  jz      short loc_140036C21
0x140036c10  mov     rax, [rcx]
0x140036c13  mov     rdx, rbx
0x140036c16  mov     rax, [rax+8]
0x140036c1a  call    _guard_dispatch_icall
0x140036c1f  mov     edi, eax
0x140036c21  mov     eax, edi
0x140036c23  add     rsp, 28h
0x140036c27  pop     rdi
0x140036c28  pop     rsi
0x140036c29  pop     rbp
0x140036c2a  pop     rbx
0x140036c2b  retn
```
