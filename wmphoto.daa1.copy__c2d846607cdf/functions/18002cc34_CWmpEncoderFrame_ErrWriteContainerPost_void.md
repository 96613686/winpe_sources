# CWmpEncoderFrame::ErrWriteContainerPost(void)

- ea: `0x18002cc34`
- end: `0x18002cec5`
- name: `?ErrWriteContainerPost@CWmpEncoderFrame@@IEAAJXZ`
- size: `657`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800297c0`
- `0x18002bfd0`

## callees

- `0x18002cc34`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::ErrWriteContainerPost(CWmpEncoderFrame *this)
{
  char *v1; // rsi
  __int64 (__fastcall *v3)(char *, __int64 *); // rax
  int v4; // ebx
  int v5; // r14d
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64 result; // rax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int128 v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h]
  __int128 v17; // [rsp+48h] [rbp-18h] BYREF
  __int64 v18; // [rsp+58h] [rbp-8h]
  __int64 v19; // [rsp+90h] [rbp+30h] BYREF
  __int64 v20; // [rsp+98h] [rbp+38h] BYREF

  v1 = (char *)this + 152;
  v3 = (__int64 (__fastcall *)(char *, __int64 *))*((_QWORD *)this + 31);
  v4 = 0;
  v19 = 0;
  v20 = 0;
  v5 = v3((char *)this + 152, &v20);
  if ( v5 >= 0 )
  {
    v6 = *((_QWORD *)this + 8317);
    v18 = 0;
    v16 = 0;
    v17 = 0;
    WORD4(v17) = -17216;
    v7 = *((_DWORD *)this + 32);
    v15 = 0;
    DWORD2(v15) = v7;
    LOWORD(v17) = 18;
    LOWORD(v15) = 19;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v6 + 72LL))(v6, 0, &v17, &v15);
    if ( v4 >= 0 )
    {
      v8 = *((_QWORD *)this + 8317);
      v18 = 0;
      v16 = 0;
      v17 = 0;
      LOWORD(v17) = 18;
      WORD4(v17) = -17215;
      v9 = *((_DWORD *)this + 33);
      v15 = 0;
      DWORD2(v15) = v9;
      LOWORD(v15) = 19;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v8 + 72LL))(
             v8,
             0,
             &v17,
             &v15);
      if ( v4 >= 0 )
      {
        if ( !*((_BYTE *)this + 96) )
          goto LABEL_20;
        v11 = *((_QWORD *)this + 8317);
        v18 = 0;
        v16 = 0;
        v17 = 0;
        LOWORD(v17) = 18;
        WORD4(v17) = -17214;
        v12 = *((_DWORD *)this + 34);
        v15 = 0;
        DWORD2(v15) = v12;
        LOWORD(v15) = 19;
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v11 + 72LL))(
               v11,
               0,
               &v17,
               &v15);
        if ( v4 >= 0 )
        {
          v13 = *((_QWORD *)this + 8317);
          v18 = 0;
          v16 = 0;
          v17 = 0;
          LOWORD(v17) = 18;
          WORD4(v17) = -17213;
          v14 = *((_DWORD *)this + 35);
          v15 = 0;
          DWORD2(v15) = v14;
          LOWORD(v15) = 19;
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v13 + 72LL))(
                 v13,
                 0,
                 &v17,
                 &v15);
          if ( v4 >= 0 )
          {
LABEL_20:
            v5 = (*((__int64 (__fastcall **)(char *, _QWORD))v1 + 11))(v1, *((unsigned int *)this + 16629));
            if ( v5 >= 0 )
            {
              v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 8317))(
                     *((_QWORD *)this + 8317),
                     &IID_IPersistStream,
                     &v19);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v19 + 48LL))(
                       v19,
                       *(_QWORD *)v1,
                       1);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 8317) + 40LL))(
                         *((_QWORD *)this + 8317),
                         (char *)this + 66520);
                  if ( v4 >= 0 )
                    v5 = (*((__int64 (__fastcall **)(char *, __int64))v1 + 11))(v1, v20);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  result = 0xFFFFFFFFLL;
  if ( !v4 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x18002cc34  mov     [rsp-28h+arg_10], rbx
0x18002cc39  mov     [rsp-28h+arg_18], rsi
0x18002cc3e  push    rbp
0x18002cc3f  push    rdi
0x18002cc40  push    r12
0x18002cc42  push    r13
0x18002cc44  push    r14
0x18002cc46  mov     rbp, rsp
0x18002cc49  sub     rsp, 60h
0x18002cc4d  lea     rsi, [rcx+98h]
0x18002cc54  mov     rdi, rcx
0x18002cc57  mov     rax, [rsi+60h]
0x18002cc5b  lea     rdx, [rbp+arg_8]
0x18002cc5f  xor     ebx, ebx
0x18002cc61  mov     rcx, rsi
0x18002cc64  mov     [rbp+arg_0], rbx
0x18002cc68  mov     [rbp+arg_8], rbx
0x18002cc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc71  mov     r14d, eax
0x18002cc74  test    eax, eax
0x18002cc76  js      loc_18002CD55
0x18002cc7c  mov     rcx, [rdi+103E8h]
0x18002cc83  lea     r12d, [rbx+12h]
0x18002cc87  xor     eax, eax
0x18002cc89  lea     r13d, [rbx+13h]
0x18002cc8d  mov     [rbp+var_8], rax
0x18002cc91  lea     r9, [rbp+var_30]
0x18002cc95  mov     [rbp+var_20], rax
0x18002cc99  lea     r8, [rbp+var_18]
0x18002cc9d  mov     eax, 0BCC0h
0x18002cca2  xorps   xmm0, xmm0
0x18002cca5  movups  [rbp+var_18], xmm0
0x18002cca9  mov     word ptr [rbp+var_18+8], ax
0x18002ccad  xor     edx, edx
0x18002ccaf  mov     eax, [rdi+80h]
0x18002ccb5  xorps   xmm1, xmm1
0x18002ccb8  movups  [rbp+var_30], xmm1
0x18002ccbc  mov     dword ptr [rbp+var_30+8], eax
0x18002ccbf  mov     word ptr [rbp+var_18], r12w
0x18002ccc4  mov     word ptr [rbp+var_30], r13w
0x18002ccc9  mov     rax, [rcx]
0x18002cccc  mov     rax, [rax+48h]
0x18002ccd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccd5  mov     ebx, eax
0x18002ccd7  test    eax, eax
0x18002ccd9  js      short loc_18002CD55
0x18002ccdb  mov     rcx, [rdi+103E8h]
0x18002cce2  lea     r9, [rbp+var_30]
0x18002cce6  xor     eax, eax
0x18002cce8  lea     r8, [rbp+var_18]
0x18002ccec  mov     [rbp+var_8], rax
0x18002ccf0  xorps   xmm0, xmm0
0x18002ccf3  mov     [rbp+var_20], rax
0x18002ccf7  xorps   xmm1, xmm1
0x18002ccfa  movups  [rbp+var_18], xmm0
0x18002ccfe  mov     eax, 0BCC1h
0x18002cd03  mov     word ptr [rbp+var_18], r12w
0x18002cd08  mov     word ptr [rbp+var_18+8], ax
0x18002cd0c  xor     edx, edx
0x18002cd0e  mov     eax, [rdi+84h]
0x18002cd14  movups  [rbp+var_30], xmm1
0x18002cd18  mov     dword ptr [rbp+var_30+8], eax
0x18002cd1b  mov     word ptr [rbp+var_30], r13w
0x18002cd20  mov     rax, [rcx]
0x18002cd23  mov     rax, [rax+48h]
0x18002cd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd2c  mov     ebx, eax
0x18002cd2e  test    eax, eax
0x18002cd30  js      short loc_18002CD55
0x18002cd32  cmp     byte ptr [rdi+60h], 0
0x18002cd36  jnz     loc_18002CE0A
0x18002cd3c  mov     edx, [rdi+103D4h]
0x18002cd42  mov     rcx, rsi
0x18002cd45  mov     rax, [rsi+58h]
0x18002cd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd4e  mov     r14d, eax
0x18002cd51  test    eax, eax
0x18002cd53  jns     short loc_18002CD8C
0x18002cd55  mov     rcx, [rbp+arg_0]
0x18002cd59  test    rcx, rcx
0x18002cd5c  jz      short loc_18002CD6A
0x18002cd5e  mov     rax, [rcx]
0x18002cd61  mov     rax, [rax+10h]
0x18002cd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd6a  or      eax, 0FFFFFFFFh
0x18002cd6d  lea     r11, [rsp+60h+var_s0]
0x18002cd72  mov     rsi, [r11+48h]
0x18002cd76  test    ebx, ebx
0x18002cd78  mov     rbx, [r11+40h]
0x18002cd7c  cmovz   eax, r14d
0x18002cd80  mov     rsp, r11
0x18002cd83  pop     r14
0x18002cd85  pop     r13
0x18002cd87  pop     r12
0x18002cd89  pop     rdi
0x18002cd8a  pop     rbp
0x18002cd8b  retn
0x18002cd8c  mov     rcx, [rdi+103E8h]
0x18002cd93  lea     r8, [rbp+arg_0]
0x18002cd97  lea     rdx, IID_IPersistStream
0x18002cd9e  mov     rax, [rcx]
0x18002cda1  mov     rax, [rax]
0x18002cda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cda9  mov     ebx, eax
0x18002cdab  test    eax, eax
0x18002cdad  js      short loc_18002CD55
0x18002cdaf  mov     rcx, [rbp+arg_0]
0x18002cdb3  mov     r8d, 1
0x18002cdb9  mov     rdx, [rsi]
0x18002cdbc  mov     rax, [rcx]
0x18002cdbf  mov     rax, [rax+30h]
0x18002cdc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdc8  mov     ebx, eax
0x18002cdca  test    eax, eax
0x18002cdcc  js      short loc_18002CD55
0x18002cdce  mov     rcx, [rdi+103E8h]
0x18002cdd5  lea     rdx, [rdi+103D8h]
0x18002cddc  mov     rax, [rcx]
0x18002cddf  mov     rax, [rax+28h]
0x18002cde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cde8  mov     ebx, eax
0x18002cdea  test    eax, eax
0x18002cdec  js      loc_18002CD55
0x18002cdf2  mov     rdx, [rbp+arg_8]
0x18002cdf6  mov     rcx, rsi
0x18002cdf9  mov     rax, [rsi+58h]
0x18002cdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce02  mov     r14d, eax
0x18002ce05  jmp     loc_18002CD55
0x18002ce0a  mov     rcx, [rdi+103E8h]
0x18002ce11  lea     r9, [rbp+var_30]
0x18002ce15  xor     eax, eax
0x18002ce17  lea     r8, [rbp+var_18]
0x18002ce1b  mov     [rbp+var_8], rax
0x18002ce1f  xorps   xmm0, xmm0
0x18002ce22  mov     [rbp+var_20], rax
0x18002ce26  xorps   xmm1, xmm1
0x18002ce29  movups  [rbp+var_18], xmm0
0x18002ce2d  mov     eax, 0BCC2h
0x18002ce32  mov     word ptr [rbp+var_18], r12w
0x18002ce37  mov     word ptr [rbp+var_18+8], ax
0x18002ce3b  xor     edx, edx
0x18002ce3d  mov     eax, [rdi+88h]
0x18002ce43  movups  [rbp+var_30], xmm1
0x18002ce47  mov     dword ptr [rbp+var_30+8], eax
0x18002ce4a  mov     word ptr [rbp+var_30], r13w
0x18002ce4f  mov     rax, [rcx]
0x18002ce52  mov     rax, [rax+48h]
0x18002ce56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce5b  mov     ebx, eax
0x18002ce5d  test    eax, eax
0x18002ce5f  js      loc_18002CD55
0x18002ce65  mov     rcx, [rdi+103E8h]
0x18002ce6c  lea     r9, [rbp+var_30]
0x18002ce70  xor     eax, eax
0x18002ce72  lea     r8, [rbp+var_18]
0x18002ce76  mov     [rbp+var_8], rax
0x18002ce7a  xorps   xmm0, xmm0
0x18002ce7d  mov     [rbp+var_20], rax
0x18002ce81  xorps   xmm1, xmm1
0x18002ce84  movups  [rbp+var_18], xmm0
0x18002ce88  mov     eax, 0BCC3h
0x18002ce8d  mov     word ptr [rbp+var_18], r12w
0x18002ce92  mov     word ptr [rbp+var_18+8], ax
0x18002ce96  xor     edx, edx
0x18002ce98  mov     eax, [rdi+8Ch]
0x18002ce9e  movups  [rbp+var_30], xmm1
0x18002cea2  mov     dword ptr [rbp+var_30+8], eax
0x18002cea5  mov     word ptr [rbp+var_30], r13w
0x18002ceaa  mov     rax, [rcx]
0x18002cead  mov     rax, [rax+48h]
0x18002ceb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ceb6  mov     ebx, eax
0x18002ceb8  test    eax, eax
0x18002ceba  js      loc_18002CD55
0x18002cec0  jmp     loc_18002CD3C
```
