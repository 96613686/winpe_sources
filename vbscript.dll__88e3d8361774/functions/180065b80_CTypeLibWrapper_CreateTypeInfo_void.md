# CTypeLibWrapper::CreateTypeInfo(void)

- ea: `0x180065b80`
- end: `0x180065dad`
- name: `?CreateTypeInfo@CTypeLibWrapper@@AEAAJXZ`
- size: `557`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180065e80`

## callees

- `0x180022ce0`
- `0x1800238f4`
- `0x180041b70`
- `0x180065b80`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180065c1d`
- `msvcrt!_ultow_s` at `0x180065c1d`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::CreateTypeInfo(CTypeLibWrapper *this)
{
  int DispatchTypeInfo; // ebx
  unsigned int v4; // esi
  unsigned int v5; // r12d
  __int64 v6; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v7; // [rsp+38h] [rbp-41h] BYREF
  struct ITypeInfo *v8; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v9[8]; // [rsp+50h] [rbp-29h] BYREF
  __int16 v10; // [rsp+70h] [rbp-9h]
  __int16 v11; // [rsp+88h] [rbp+Fh]
  int v12; // [rsp+8Ch] [rbp+13h]
  wchar_t Buffer[12]; // [rsp+90h] [rbp+17h] BYREF

  v8 = 0;
  v6 = 0;
  if ( !(unsigned int)MUTX::Enter((CTypeLibWrapper *)((char *)this + 48)) )
    return 2147500037LL;
  if ( *((_QWORD *)this + 5) )
  {
    DispatchTypeInfo = 0;
  }
  else
  {
    DispatchTypeInfo = GetDispatchTypeInfo(&v8);
    if ( DispatchTypeInfo >= 0 )
    {
      memset(Buffer, 0, 22);
      _ultow_s(_InterlockedIncrement(&dword_180090828), Buffer, 0xBu, 10);
      DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, __int64, __int64 *))(**((_QWORD **)this + 4)
                                                                                          + 24LL))(
                           *((_QWORD *)this + 4),
                           Buffer,
                           4,
                           &v6);
      if ( DispatchTypeInfo >= 0 )
      {
        v7 = 0;
        DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, struct ITypeInfo *, unsigned int *))(*(_QWORD *)v6 + 64LL))(
                             v6,
                             v8,
                             &v7);
        if ( DispatchTypeInfo >= 0 )
        {
          DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 80LL))(v6, 0, v7);
          if ( DispatchTypeInfo >= 0 )
          {
            memset_0(v9, 0, 0x40u);
            v12 = 3;
            v10 = 12;
            v4 = 0;
            v11 = 0;
            if ( *((_DWORD *)this + 3) )
            {
              while ( 1 )
              {
                v5 = v4 + 1;
                v9[0] = v4 + 1;
                DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v6 + 112LL))(
                                     v6,
                                     v4,
                                     v9);
                if ( DispatchTypeInfo < 0 )
                  break;
                DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 128LL))(
                                     v6,
                                     v4,
                                     *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 16LL * v4 + 8));
                if ( DispatchTypeInfo < 0 )
                  break;
                ++v4;
                if ( v5 >= *((_DWORD *)this + 3) )
                  goto LABEL_13;
              }
            }
            else
            {
LABEL_13:
              DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 200LL))(v6);
              if ( DispatchTypeInfo >= 0 )
                DispatchTypeInfo = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v6)(
                                     v6,
                                     &IID_ITypeInfo,
                                     (char *)this + 40);
            }
          }
        }
      }
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v8 )
    ((void (__fastcall *)(struct ITypeInfo *))v8->lpVtbl->Release)(v8);
  MUTX::Leave((CTypeLibWrapper *)((char *)this + 48));
  return (unsigned int)DispatchTypeInfo;
}

```

## disassembly

```asm
0x180065b80  mov     [rsp-8+arg_8], rbx
0x180065b85  mov     [rsp-8+arg_10], rsi
0x180065b8a  push    rbp
0x180065b8b  push    rdi
0x180065b8c  push    r12
0x180065b8e  push    r14
0x180065b90  push    r15
0x180065b92  lea     rbp, [rsp-37h]
0x180065b97  sub     rsp, 0B0h
0x180065b9e  mov     rax, cs:__security_cookie
0x180065ba5  xor     rax, rsp
0x180065ba8  mov     [rbp+57h+var_28], rax
0x180065bac  mov     rdi, rcx
0x180065baf  mov     [rbp+57h+var_90], 0
0x180065bb7  add     rcx, 30h ; '0'; this
0x180065bbb  mov     [rbp+57h+var_A0], 0
0x180065bc3  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180065bc8  test    eax, eax
0x180065bca  jnz     short loc_180065BD6
0x180065bcc  mov     eax, 80004005h
0x180065bd1  jmp     loc_180065D85
0x180065bd6  cmp     qword ptr [rdi+28h], 0
0x180065bdb  jz      short loc_180065BE4
0x180065bdd  xor     ebx, ebx
0x180065bdf  jmp     loc_180065D50
0x180065be4  lea     rcx, [rbp+57h+var_90]; struct ITypeInfo **
0x180065be8  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x180065bed  mov     ebx, eax
0x180065bef  test    eax, eax
0x180065bf1  js      loc_180065D50
0x180065bf7  xor     eax, eax
0x180065bf9  xorps   xmm0, xmm0
0x180065bfc  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180065c00  mov     qword ptr [rbp+57h+Buffer+0Eh], rax
0x180065c04  lea     ecx, [rax+1]
0x180065c07  lock xadd cs:dword_180090828, ecx
0x180065c0f  inc     ecx; Value
0x180065c11  lea     r9d, [rax+0Ah]; Radix
0x180065c15  lea     r8d, [rax+0Bh]; BufferCount
0x180065c19  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180065c1d  call    cs:__imp__ultow_s
0x180065c23  mov     rcx, [rdi+20h]
0x180065c27  lea     r9, [rbp+57h+var_A0]
0x180065c2b  mov     r8d, 4
0x180065c31  lea     rdx, [rbp+57h+Buffer]
0x180065c35  mov     rax, [rcx]
0x180065c38  mov     rax, [rax+18h]
0x180065c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c41  mov     ebx, eax
0x180065c43  test    eax, eax
0x180065c45  js      loc_180065D50
0x180065c4b  mov     rcx, [rbp+57h+var_A0]
0x180065c4f  lea     r8, [rbp+57h+var_98]
0x180065c53  mov     rdx, [rbp+57h+var_90]
0x180065c57  mov     [rbp+57h+var_98], 0
0x180065c5e  mov     rax, [rcx]
0x180065c61  mov     rax, [rax+40h]
0x180065c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c6a  mov     ebx, eax
0x180065c6c  test    eax, eax
0x180065c6e  js      loc_180065D50
0x180065c74  mov     rcx, [rbp+57h+var_A0]
0x180065c78  xor     edx, edx
0x180065c7a  mov     r8d, [rbp+57h+var_98]
0x180065c7e  mov     rax, [rcx]
0x180065c81  mov     rax, [rax+50h]
0x180065c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c8a  mov     ebx, eax
0x180065c8c  test    eax, eax
0x180065c8e  js      loc_180065D50
0x180065c94  xor     edx, edx; Val
0x180065c96  lea     rcx, [rbp+57h+var_80]; void *
0x180065c9a  lea     r8d, [rdx+40h]; Size
0x180065c9e  call    memset_0
0x180065ca3  mov     eax, 0Ch
0x180065ca8  mov     [rbp+57h+var_44], 3
0x180065caf  mov     [rbp+57h+var_60], ax
0x180065cb3  xor     esi, esi
0x180065cb5  xor     eax, eax
0x180065cb7  mov     [rbp+57h+var_48], ax
0x180065cbb  cmp     [rdi+0Ch], eax
0x180065cbe  jbe     short loc_180065D1B
0x180065cc0  mov     rcx, [rbp+57h+var_A0]
0x180065cc4  lea     r12d, [rsi+1]
0x180065cc8  mov     [rbp+57h+var_80], r12d
0x180065ccc  lea     r8, [rbp+57h+var_80]
0x180065cd0  mov     edx, esi
0x180065cd2  mov     rax, [rcx]
0x180065cd5  mov     rax, [rax+70h]
0x180065cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cde  mov     ebx, eax
0x180065ce0  test    eax, eax
0x180065ce2  js      short loc_180065D50
0x180065ce4  mov     rax, [rdi+10h]
0x180065ce8  mov     edx, esi
0x180065cea  mov     rcx, [rbp+57h+var_A0]
0x180065cee  mov     r10d, esi
0x180065cf1  add     r10, r10
0x180065cf4  mov     r8, [rax+18h]
0x180065cf8  mov     r9, [rcx]
0x180065cfb  mov     r8, [r8+r10*8+8]
0x180065d00  mov     rax, [r9+80h]
0x180065d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d0c  mov     ebx, eax
0x180065d0e  test    eax, eax
0x180065d10  js      short loc_180065D50
0x180065d12  mov     esi, r12d
0x180065d15  cmp     r12d, [rdi+0Ch]
0x180065d19  jb      short loc_180065CC0
0x180065d1b  mov     rcx, [rbp+57h+var_A0]
0x180065d1f  mov     rax, [rcx]
0x180065d22  mov     rax, [rax+0C8h]
0x180065d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d2e  mov     ebx, eax
0x180065d30  test    eax, eax
0x180065d32  js      short loc_180065D50
0x180065d34  mov     rcx, [rbp+57h+var_A0]
0x180065d38  lea     r8, [rdi+28h]
0x180065d3c  lea     rdx, IID_ITypeInfo
0x180065d43  mov     rax, [rcx]
0x180065d46  mov     rax, [rax]
0x180065d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d4e  mov     ebx, eax
0x180065d50  mov     rcx, [rbp+57h+var_A0]
0x180065d54  test    rcx, rcx
0x180065d57  jz      short loc_180065D65
0x180065d59  mov     rax, [rcx]
0x180065d5c  mov     rax, [rax+10h]
0x180065d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d65  mov     rcx, [rbp+57h+var_90]
0x180065d69  test    rcx, rcx
0x180065d6c  jz      short loc_180065D7A
0x180065d6e  mov     rax, [rcx]
0x180065d71  mov     rax, [rax+10h]
0x180065d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d7a  lea     rcx, [rdi+30h]; this
0x180065d7e  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180065d83  mov     eax, ebx
0x180065d85  mov     rcx, [rbp+57h+var_28]
0x180065d89  xor     rcx, rsp; StackCookie
0x180065d8c  call    __security_check_cookie
0x180065d91  lea     r11, [rsp+0D0h+var_20]
0x180065d99  mov     rbx, [r11+38h]
0x180065d9d  mov     rsi, [r11+40h]
0x180065da1  mov     rsp, r11
0x180065da4  pop     r15
0x180065da6  pop     r14
0x180065da8  pop     r12
0x180065daa  pop     rdi
0x180065dab  pop     rbp
0x180065dac  retn
```
