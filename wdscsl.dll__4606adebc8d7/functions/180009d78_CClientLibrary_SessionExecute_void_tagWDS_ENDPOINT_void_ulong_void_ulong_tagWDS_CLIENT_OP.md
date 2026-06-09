# CClientLibrary::SessionExecute(void *,tagWDS_ENDPOINT *,void *,ulong,void * *,ulong *,tagWDS_CLIENT_OP *)

- ea: `0x180009d78`
- end: `0x180009fc2`
- name: `?SessionExecute@CClientLibrary@@QEAAKPEAXPEAUtagWDS_ENDPOINT@@0KPEAPEAXPEAKPEAUtagWDS_CLIENT_OP@@@Z`
- size: `586`
- prototype: `unsigned int(CClientLibrary *__hidden this, void *, struct tagWDS_ENDPOINT *, void *, unsigned int, void **, unsigned int *, struct tagWDS_CLIENT_OP *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ceb0`
- `0x18000d120`

## callees

- `0x180005558`
- `0x1800059f8`
- `0x180009d78`
- `0x18000bd5c`

## import_xrefs

- `WdsCommonLib!?IsBroadcastAddress@CNetworkAddress@@SAHPEAUtagWDS_ENDPOINT@@@Z` at `0x180009e50`
- `WdsCommonLib!?IsBroadcastAddress@CNetworkAddress@@SAHPEAUtagWDS_ENDPOINT@@@Z` at `0x180009e50`

## pseudocode

```c
__int64 __fastcall CClientLibrary::SessionExecute(
        CClientLibrary *this,
        unsigned int *a2,
        struct tagWDS_ENDPOINT *a3,
        void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7,
        struct tagWDS_CLIENT_OP *a8)
{
  unsigned int v8; // r12d
  unsigned int v11; // ebx
  CClientLibrary *v12; // rcx
  DWORD v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // r9d
  unsigned int v17; // eax
  __int64 v18; // rdx
  bool v19; // zf
  bool v20; // zf
  unsigned int v21; // eax
  struct tagWDS_ENDPOINT *v23; // [rsp+80h] [rbp+18h]

  v23 = a3;
  v8 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 10, 0) )
  {
    if ( !a2 || !a4 || !a5 || !a6 || !a7 )
      return 87;
    while ( 1 )
    {
      v12 = (CClientLibrary *)a2[264];
      if ( (_DWORD)v12 )
      {
        if ( (_DWORD)v12 != 1 )
          return 6;
        v13 = a8 ? *(_DWORD *)a8 : -1;
        v14 = CClientLibrary::ExecuteRpcSession(v12, (struct Session *)a2, a4, a5, a6, a7, v13);
        v16 = 1705;
      }
      else
      {
        if ( !a3 )
        {
          if ( CNetworkAddress::IsBroadcastAddress((struct tagWDS_ENDPOINT *)(a2 + 263)) )
            return 87;
          a3 = v23;
        }
        v17 = a8 ? *(_DWORD *)a8 : -1;
        v14 = CClientLibrary::ExecuteUdpSession(v12, (struct Session *)a2, a3, a4, a5, a6, a7, v17);
        v16 = 1696;
      }
      v11 = ElValidateWin32(v14, v15, (__int64)"base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", v16);
      if ( !(unsigned int)ElValidateWin32(v11, v18, (__int64)"base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 0x6B1u)
        || !a8 )
      {
        return v11;
      }
      ++v8;
      if ( v11 <= 0x6DF )
        break;
      if ( v11 <= 0x71C )
      {
        if ( v11 == 1820 || v11 == 1761 || v11 == 1762 || v11 == 1766 || v11 == 1768 )
          goto LABEL_54;
        v21 = v11 - 1817;
        v20 = v11 == 1817;
LABEL_38:
        if ( v20 )
          goto LABEL_54;
        v19 = v21 == 1;
        goto LABEL_53;
      }
      if ( v11 == 10051 || v11 == 10052 || v11 == 10061 || v11 == 10064 || v11 == 10065 )
        goto LABEL_54;
      v19 = v11 == 10071;
LABEL_53:
      if ( !v19 )
        return v11;
LABEL_54:
      if ( v8 > *((_DWORD *)a8 + 1) )
        return v11;
      a3 = v23;
    }
    if ( v11 == 1759 )
      goto LABEL_54;
    if ( v11 <= 0x6BA )
    {
      if ( v11 == 1722 || v11 == 1460 || v11 == 1707 || v11 == 1708 || v11 == 1710 || v11 == 1715 )
        goto LABEL_54;
      v19 = v11 == 1720;
      goto LABEL_53;
    }
    if ( v11 == 1723 || v11 == 1726 || v11 == 1727 || v11 == 1728 )
      goto LABEL_54;
    v21 = v11 - 1752;
    v20 = v11 == 1752;
    goto LABEL_38;
  }
  return 5023;
}

```

## disassembly

```asm
0x180009d78  mov     rax, rsp
0x180009d7b  mov     [rax+8], rbx
0x180009d7f  mov     [rax+10h], rbp
0x180009d83  mov     [rax+20h], rsi
0x180009d87  mov     [rax+18h], r8
0x180009d8b  push    rdi
0x180009d8c  push    r12
0x180009d8e  push    r13
0x180009d90  push    r14
0x180009d92  push    r15
0x180009d94  sub     rsp, 40h
0x180009d98  xor     r12d, r12d
0x180009d9b  mov     r13, r9
0x180009d9e  xor     eax, eax
0x180009da0  mov     rsi, rdx
0x180009da3  lock xadd [rcx+28h], eax
0x180009da8  test    eax, eax
0x180009daa  jnz     short loc_180009DB6
0x180009dac  mov     ebx, 139Fh
0x180009db1  jmp     loc_180009FA1
0x180009db6  test    rsi, rsi
0x180009db9  jz      loc_180009F9C
0x180009dbf  test    r13, r13
0x180009dc2  jz      loc_180009F9C
0x180009dc8  mov     ebp, [rsp+68h+arg_20]
0x180009dcf  test    ebp, ebp
0x180009dd1  jz      loc_180009F9C
0x180009dd7  mov     r14, [rsp+68h+arg_28]
0x180009ddf  test    r14, r14
0x180009de2  jz      loc_180009F9C
0x180009de8  mov     r15, [rsp+68h+arg_30]
0x180009df0  test    r15, r15
0x180009df3  jz      loc_180009F9C
0x180009df9  mov     rdi, [rsp+68h+arg_38]
0x180009e01  mov     ecx, [rsi+420h]; this
0x180009e07  test    ecx, ecx
0x180009e09  jz      short loc_180009E44
0x180009e0b  cmp     ecx, 1
0x180009e0e  jnz     loc_180009F95
0x180009e14  test    rdi, rdi
0x180009e17  jz      short loc_180009E1D
0x180009e19  mov     eax, [rdi]
0x180009e1b  jmp     short loc_180009E20
0x180009e1d  or      eax, 0FFFFFFFFh
0x180009e20  mov     dword ptr [rsp+68h+var_38], eax; unsigned int
0x180009e24  mov     r9d, ebp; unsigned int
0x180009e27  mov     [rsp+68h+var_40], r15; unsigned int *
0x180009e2c  mov     r8, r13; void *
0x180009e2f  mov     rdx, rsi; struct Session *
0x180009e32  mov     [rsp+68h+var_48], r14; void **
0x180009e37  call    ?ExecuteRpcSession@CClientLibrary@@AEAAKPEAUSession@1@PEAXKPEAPEAXPEAKK@Z; CClientLibrary::ExecuteRpcSession(CClientLibrary::Session *,void *,ulong,void * *,ulong *,ulong)
0x180009e3c  mov     r9d, 6A9h
0x180009e42  jmp     short loc_180009E9B
0x180009e44  test    r8, r8
0x180009e47  jnz     short loc_180009E6C
0x180009e49  lea     rcx, [rsi+41Ch]
0x180009e50  call    cs:__imp_?IsBroadcastAddress@CNetworkAddress@@SAHPEAUtagWDS_ENDPOINT@@@Z; CNetworkAddress::IsBroadcastAddress(tagWDS_ENDPOINT *)
0x180009e57  nop     dword ptr [rax+rax+00h]
0x180009e5c  test    eax, eax
0x180009e5e  jnz     loc_180009F9C
0x180009e64  mov     r8, [rsp+68h+arg_10]; struct tagWDS_ENDPOINT *
0x180009e6c  test    rdi, rdi
0x180009e6f  jz      short loc_180009E75
0x180009e71  mov     eax, [rdi]
0x180009e73  jmp     short loc_180009E78
0x180009e75  or      eax, 0FFFFFFFFh
0x180009e78  mov     [rsp+68h+var_30], eax; unsigned int
0x180009e7c  mov     r9, r13; void *
0x180009e7f  mov     [rsp+68h+var_38], r15; unsigned int *
0x180009e84  mov     rdx, rsi; struct Session *
0x180009e87  mov     [rsp+68h+var_40], r14; void **
0x180009e8c  mov     dword ptr [rsp+68h+var_48], ebp; unsigned int
0x180009e90  call    ?ExecuteUdpSession@CClientLibrary@@AEAAKPEAUSession@1@PEAUtagWDS_ENDPOINT@@PEAXKPEAPEAXPEAKK@Z; CClientLibrary::ExecuteUdpSession(CClientLibrary::Session *,tagWDS_ENDPOINT *,void *,ulong,void * *,ulong *,ulong)
0x180009e95  mov     r9d, 6A0h
0x180009e9b  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180009ea2  mov     ecx, eax
0x180009ea4  call    ElValidateWin32
0x180009ea9  mov     r9d, 6B1h
0x180009eaf  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180009eb6  mov     ecx, eax
0x180009eb8  mov     ebx, eax
0x180009eba  call    ElValidateWin32
0x180009ebf  test    eax, eax
0x180009ec1  jz      loc_180009FA1
0x180009ec7  test    rdi, rdi
0x180009eca  jz      loc_180009FA1
0x180009ed0  inc     r12d
0x180009ed3  cmp     ebx, 6DFh
0x180009ed9  ja      short loc_180009F39
0x180009edb  jz      loc_180009F82
0x180009ee1  cmp     ebx, 6BAh
0x180009ee7  ja      short loc_180009F17
0x180009ee9  jz      loc_180009F82
0x180009eef  mov     eax, ebx
0x180009ef1  sub     eax, 5B4h
0x180009ef6  jz      loc_180009F82
0x180009efc  sub     eax, 0F7h
0x180009f01  jz      short loc_180009F82
0x180009f03  sub     eax, 1
0x180009f06  jz      short loc_180009F82
0x180009f08  sub     eax, 2
0x180009f0b  jz      short loc_180009F82
0x180009f0d  sub     eax, 5
0x180009f10  jz      short loc_180009F82
0x180009f12  cmp     eax, 5
0x180009f15  jmp     short loc_180009F80
0x180009f17  mov     eax, ebx
0x180009f19  sub     eax, 6BBh
0x180009f1e  jz      short loc_180009F82
0x180009f20  sub     eax, 3
0x180009f23  jz      short loc_180009F82
0x180009f25  sub     eax, 1
0x180009f28  jz      short loc_180009F82
0x180009f2a  sub     eax, 1
0x180009f2d  jz      short loc_180009F82
0x180009f2f  sub     eax, 18h
0x180009f32  jz      short loc_180009F82
0x180009f34  cmp     eax, 1
0x180009f37  jmp     short loc_180009F80
0x180009f39  cmp     ebx, 71Ch
0x180009f3f  ja      short loc_180009F60
0x180009f41  jz      short loc_180009F82
0x180009f43  mov     eax, ebx
0x180009f45  sub     eax, 6E1h
0x180009f4a  jz      short loc_180009F82
0x180009f4c  sub     eax, 1
0x180009f4f  jz      short loc_180009F82
0x180009f51  sub     eax, 4
0x180009f54  jz      short loc_180009F82
0x180009f56  sub     eax, 2
0x180009f59  jz      short loc_180009F82
0x180009f5b  sub     eax, 31h ; '1'
0x180009f5e  jmp     short loc_180009F32
0x180009f60  mov     eax, ebx
0x180009f62  sub     eax, 2743h
0x180009f67  jz      short loc_180009F82
0x180009f69  sub     eax, 1
0x180009f6c  jz      short loc_180009F82
0x180009f6e  sub     eax, 9
0x180009f71  jz      short loc_180009F82
0x180009f73  sub     eax, 3
0x180009f76  jz      short loc_180009F82
0x180009f78  sub     eax, 1
0x180009f7b  jz      short loc_180009F82
0x180009f7d  cmp     eax, 6
0x180009f80  jnz     short loc_180009FA1
0x180009f82  cmp     r12d, [rdi+4]
0x180009f86  ja      short loc_180009FA1
0x180009f88  mov     r8, [rsp+68h+arg_10]
0x180009f90  jmp     loc_180009E01
0x180009f95  mov     ebx, 6
0x180009f9a  jmp     short loc_180009FA1
0x180009f9c  mov     ebx, 57h ; 'W'
0x180009fa1  lea     r11, [rsp+68h+var_28]
0x180009fa6  mov     eax, ebx
0x180009fa8  mov     rbx, [r11+30h]
0x180009fac  mov     rbp, [r11+38h]
0x180009fb0  mov     rsi, [r11+48h]
0x180009fb4  mov     rsp, r11
0x180009fb7  pop     r15
0x180009fb9  pop     r14
0x180009fbb  pop     r13
0x180009fbd  pop     r12
0x180009fbf  pop     rdi
0x180009fc0  retn
```
