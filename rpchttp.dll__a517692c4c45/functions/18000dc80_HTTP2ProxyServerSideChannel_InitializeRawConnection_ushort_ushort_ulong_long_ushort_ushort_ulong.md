# HTTP2ProxyServerSideChannel::InitializeRawConnection(ushort *,ushort,ulong,long (*)(ushort *,ushort *,ulong))

- ea: `0x18000dc80`
- end: `0x18000deaa`
- name: `?InitializeRawConnection@HTTP2ProxyServerSideChannel@@QEAAJPEAGGKP6AJ00K@Z@Z`
- size: `554`
- prototype: `__int64 __fastcall(HTTP2ProxyServerSideChannel *this, unsigned __int16 *, unsigned __int16, __int64, int (*)(unsigned __int16 *, unsigned __int16 *, unsigned int))`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007e74`
- `0x180007ef0`

## callees

- `0x18000dc80`
- `0x18001e33c`
- `0x180024629`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!_itow_s` at `0x18000ddd7`
- `ntdll!_itow_s` at `0x18000ddd7`
- `RPCRT4!I_RpcFree` at `0x18000de7b`
- `RPCRT4!I_RpcFree` at `0x18000de7b`

## string_xrefs

- `0x18000de1c`: `security=anonymous static false`

## pseudocode

```c
__int64 __fastcall HTTP2ProxyServerSideChannel::InitializeRawConnection(
        HTTP2ProxyServerSideChannel *this,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        __int64 a4,
        int (*a5)(unsigned __int16 *, unsigned __int16 *, unsigned int))
{
  unsigned int v6; // ebx
  unsigned __int16 v8; // ax
  unsigned int v9; // r8d
  unsigned __int16 *v10; // rdx
  int v11; // ecx
  __int64 v12; // r8
  unsigned int v13; // ebx
  unsigned int i; // r8d
  unsigned __int16 v15; // ax
  const unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rdi
  _BYTE v20[144]; // [rsp+80h] [rbp-D8h] BYREF
  wchar_t Buffer[8]; // [rsp+110h] [rbp-48h] BYREF

  v6 = a3;
  memset_0(v20, 0, sizeof(v20));
  if ( *((_DWORD *)this + 20) )
  {
    _itow_s(v6, Buffer, 7u, 10);
    if ( ((unsigned int (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD))a5)(a2, 0, v6) )
    {
      return 1722;
    }
    else
    {
      v17 = DuplicateString2(v16, Buffer);
      v18 = v17;
      if ( v17 )
      {
        v13 = (*((__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, unsigned __int16 *, const wchar_t *, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD))pRuntimeImportTable
               + 90))(
                *((_QWORD *)this + 9),
                L"ncacn_np",
                L".",
                v17,
                L"security=anonymous static false",
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0);
        I_RpcFree(v18);
      }
      else
      {
        return 14;
      }
    }
  }
  else
  {
    v8 = *a2;
    v9 = 0;
    if ( *a2 )
    {
      v10 = a2;
      do
      {
        ++v10;
        v11 = 1048583 * v8;
        v8 = *v10;
        v9 += v11;
      }
      while ( *v10 );
    }
    v12 = v9 % 0xA;
    if ( _InterlockedIncrement((volatile signed __int32 *)&HTTP2ProxyServerSideChannel::RateLimitBuckets + v12) < 100 )
    {
      v13 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, _QWORD, _DWORD, _DWORD, _BYTE *, _DWORD, int, int, int (*)(unsigned __int16 *, unsigned __int16 *, unsigned int)))pRuntimeImportTable
             + 10))(
              *((_QWORD *)this + 9),
              a2,
              (unsigned __int16)v6,
              0,
              0,
              0,
              v20,
              0,
              36000,
              1,
              a5);
      for ( i = 0; ; i += 1048583 * v15 )
      {
        v15 = *a2;
        if ( !*a2 )
          break;
        ++a2;
      }
      _InterlockedDecrement((volatile signed __int32 *)&HTTP2ProxyServerSideChannel::RateLimitBuckets + i % 0xA);
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)&HTTP2ProxyServerSideChannel::RateLimitBuckets + v12);
      return 1723;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18000dc80  mov     [rsp+arg_18], rbx
0x18000dc85  push    rbp
0x18000dc86  push    rsi
0x18000dc87  push    rdi
0x18000dc88  push    r14
0x18000dc8a  push    r15
0x18000dc8c  sub     rsp, 130h
0x18000dc93  mov     rax, cs:__security_cookie
0x18000dc9a  xor     rax, rsp
0x18000dc9d  mov     [rsp+158h+var_38], rax
0x18000dca5  mov     rbp, [rsp+158h+arg_20]
0x18000dcad  mov     rdi, rdx
0x18000dcb0  movzx   ebx, r8w
0x18000dcb4  mov     rsi, rcx
0x18000dcb7  xor     edx, edx; Val
0x18000dcb9  lea     rcx, [rsp+158h+var_D8]; void *
0x18000dcc1  mov     r8d, 90h; Size
0x18000dcc7  call    memset_0
0x18000dccc  xor     r14d, r14d
0x18000dccf  cmp     [rsi+50h], r14d
0x18000dcd3  jnz     loc_18000DDC3
0x18000dcd9  movzx   eax, word ptr [rdi]
0x18000dcdc  mov     r8d, r14d
0x18000dcdf  test    ax, ax
0x18000dce2  jz      short loc_18000DCFF
0x18000dce4  mov     rdx, rdi
0x18000dce7  movzx   eax, ax
0x18000dcea  lea     rdx, [rdx+2]
0x18000dcee  imul    ecx, eax, 100007h
0x18000dcf4  movzx   eax, word ptr [rdx]
0x18000dcf7  add     r8d, ecx
0x18000dcfa  test    ax, ax
0x18000dcfd  jnz     short loc_18000DCE7
0x18000dcff  mov     eax, 0CCCCCCCDh
0x18000dd04  lea     r15, ?RateLimitBuckets@HTTP2ProxyServerSideChannel@@1PAJA; long near * HTTP2ProxyServerSideChannel::RateLimitBuckets
0x18000dd0b  mul     r8d
0x18000dd0e  shr     edx, 3
0x18000dd11  lea     eax, [rdx+rdx*4]
0x18000dd14  mov     edx, 1
0x18000dd19  add     eax, eax
0x18000dd1b  sub     r8d, eax
0x18000dd1e  mov     eax, edx
0x18000dd20  lock xadd [r15+r8*4], eax
0x18000dd26  add     eax, edx
0x18000dd28  cmp     eax, 64h ; 'd'
0x18000dd2b  jl      short loc_18000DD3C
0x18000dd2d  lock dec dword ptr [r15+r8*4]
0x18000dd32  mov     ebx, 6BBh
0x18000dd37  jmp     loc_18000DE81
0x18000dd3c  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000dd43  lea     rcx, [rsp+158h+var_D8]
0x18000dd4b  mov     [rsp+158h+var_108], rbp
0x18000dd50  xor     r9d, r9d
0x18000dd53  mov     [rsp+158h+var_110], edx
0x18000dd57  movzx   r8d, bx
0x18000dd5b  mov     dword ptr [rsp+158h+var_118], 8CA0h
0x18000dd63  mov     rdx, rdi
0x18000dd66  mov     rax, [rax+50h]
0x18000dd6a  mov     [rsp+158h+var_120], r14d
0x18000dd6f  mov     [rsp+158h+var_128], rcx
0x18000dd74  mov     rcx, [rsi+48h]
0x18000dd78  mov     [rsp+158h+var_130], r14d
0x18000dd7d  mov     dword ptr [rsp+158h+var_138], r14d
0x18000dd82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd87  mov     ebx, eax
0x18000dd89  mov     r8d, r14d
0x18000dd8c  jmp     short loc_18000DD9E
0x18000dd8e  movzx   eax, ax
0x18000dd91  lea     rdi, [rdi+2]
0x18000dd95  imul    ecx, eax, 100007h
0x18000dd9b  add     r8d, ecx
0x18000dd9e  movzx   eax, word ptr [rdi]
0x18000dda1  test    ax, ax
0x18000dda4  jnz     short loc_18000DD8E
0x18000dda6  mov     eax, 0CCCCCCCDh
0x18000ddab  mul     r8d
0x18000ddae  shr     edx, 3
0x18000ddb1  lea     eax, [rdx+rdx*4]
0x18000ddb4  add     eax, eax
0x18000ddb6  sub     r8d, eax
0x18000ddb9  lock dec dword ptr [r15+r8*4]
0x18000ddbe  jmp     loc_18000DE81
0x18000ddc3  mov     r9d, 0Ah; Radix
0x18000ddc9  lea     rdx, [rsp+158h+Buffer]; Buffer
0x18000ddd1  mov     ecx, ebx; Value
0x18000ddd3  lea     r8d, [r9-3]; BufferCount
0x18000ddd7  call    cs:__imp__itow_s
0x18000dddd  mov     r8d, ebx
0x18000dde0  xor     edx, edx
0x18000dde2  mov     rcx, rdi
0x18000dde5  mov     rax, rbp
0x18000dde8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dded  test    eax, eax
0x18000ddef  jz      short loc_18000DDFB
0x18000ddf1  mov     ebx, 6BAh
0x18000ddf6  jmp     loc_18000DE81
0x18000ddfb  lea     rdx, [rsp+158h+Buffer]; unsigned __int16 *
0x18000de03  call    ?DuplicateString2@@YAPEAGPEBG0@Z; DuplicateString2(ushort const *,ushort const *)
0x18000de08  mov     rdi, rax
0x18000de0b  test    rax, rax
0x18000de0e  jnz     short loc_18000DE15
0x18000de10  lea     ebx, [rax+0Eh]
0x18000de13  jmp     short loc_18000DE81
0x18000de15  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000de1c  lea     rcx, aSecurityAnonym; "security=anonymous static false"
0x18000de23  mov     [rsp+158h+var_F0], r14
0x18000de28  lea     r8, asc_180028240; "."
0x18000de2f  mov     [rsp+158h+var_F8], r14
0x18000de34  lea     rdx, aNcacnNp; "ncacn_np"
0x18000de3b  mov     [rsp+158h+var_100], r14d
0x18000de40  mov     r9, rdi
0x18000de43  mov     rax, [rax+2D0h]
0x18000de4a  mov     dword ptr [rsp+158h+var_108], r14d
0x18000de4f  mov     [rsp+158h+var_110], r14d
0x18000de54  mov     [rsp+158h+var_118], r14
0x18000de59  mov     [rsp+158h+var_120], r14d
0x18000de5e  mov     dword ptr [rsp+158h+var_128], r14d
0x18000de63  mov     [rsp+158h+var_130], r14d
0x18000de68  mov     [rsp+158h+var_138], rcx
0x18000de6d  mov     rcx, [rsi+48h]
0x18000de71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de76  mov     ebx, eax
0x18000de78  mov     rcx, rdi; Object
0x18000de7b  call    cs:__imp_I_RpcFree
0x18000de81  mov     eax, ebx
0x18000de83  mov     rcx, [rsp+158h+var_38]
0x18000de8b  xor     rcx, rsp; StackCookie
0x18000de8e  call    __security_check_cookie
0x18000de93  mov     rbx, [rsp+158h+arg_18]
0x18000de9b  add     rsp, 130h
0x18000dea2  pop     r15
0x18000dea4  pop     r14
0x18000dea6  pop     rdi
0x18000dea7  pop     rsi
0x18000dea8  pop     rbp
0x18000dea9  retn
```
