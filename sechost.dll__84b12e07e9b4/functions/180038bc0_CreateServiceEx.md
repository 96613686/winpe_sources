# CreateServiceEx

- ea: `0x180038bc0`
- end: `0x180038f77`
- name: `CreateServiceEx`
- size: `951`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180038bc0`
- `0x18003c4c0`
- `0x18003c588`
- `0x18003c650`
- `0x18004a934`
- `0x18004aa18`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038f52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038f52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038f46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038f46`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050573`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050595`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800505b7`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800505d9`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050573`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050595`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800505b7`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800505d9`

## pseudocode

```c
__int64 __fastcall CreateServiceEx(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  int v15; // r10d
  int v16; // r11d
  int v17; // r12d
  int v18; // r14d
  __int16 v19; // si
  DWORD v20; // eax
  DWORD v22; // ebx
  int v23; // [rsp+98h] [rbp-50h] BYREF
  int v24; // [rsp+9Ch] [rbp-4Ch]
  HLOCAL hMem; // [rsp+A0h] [rbp-48h] BYREF
  _QWORD v26[8]; // [rsp+A8h] [rbp-40h] BYREF

  v15 = a3;
  v16 = a2;
  v17 = a1;
  v26[0] = 0;
  hMem = 0;
  v23 = 0;
  v18 = 0;
  v24 = 0;
  v19 = 0;
  if ( a13 )
  {
    v20 = ScEncryptPassword(a1, a13, &hMem, &v23);
    if ( v20 )
    {
      SetLastError(v20);
      return 0;
    }
    v15 = a3;
    v16 = a2;
  }
  if ( a11 )
  {
    v18 = ScWStrArraySize(a11);
    v24 = v18;
  }
  if ( a14 )
  {
    if ( *(_BYTE *)a14 != 1 )
    {
      SetLastError(0x57u);
      return 0;
    }
    if ( *(_WORD *)(a14 + 2) )
      v19 = *(_WORD *)(a14 + 2);
  }
  if ( v19 )
  {
    v22 = RCreateWowService(
            v17,
            v16,
            v15,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9,
            a10,
            a11,
            v18,
            a12,
            (__int64)hMem,
            v23,
            v19,
            (__int64)v26);
    if ( v22 == 120 )
    {
      if ( v19 != 332
        || (v22 = RCreateServiceWOW64W(
                    v17,
                    a2,
                    a3,
                    a4,
                    a5,
                    a6,
                    a7,
                    a8,
                    a9,
                    a10,
                    a11,
                    v18,
                    a12,
                    (__int64)hMem,
                    v23,
                    (__int64)v26),
            v22 == 120) )
      {
        v22 = 87;
      }
    }
  }
  else
  {
    v22 = RCreateServiceW(v17, v16, v15, a4, a5, a6, a7, a8, a9, a10, a11, v18, a12, (__int64)hMem, v23, (__int64)v26);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( !v22 )
    return v26[0];
  SetLastError(v22);
  return 0;
}

```

## disassembly

```asm
0x180038bc0  mov     rax, rsp
0x180038bc3  mov     [rax+20h], r9d
0x180038bc7  mov     [rax+18h], r8
0x180038bcb  mov     [rax+10h], rdx
0x180038bcf  mov     [rax+8], rcx
0x180038bd3  push    rbx
0x180038bd4  push    rsi
0x180038bd5  push    rdi
0x180038bd6  push    r12
0x180038bd8  push    r13
0x180038bda  push    r14
0x180038bdc  push    r15
0x180038bde  sub     rsp, 0B0h
0x180038be5  mov     r13d, r9d
0x180038be8  mov     r10, r8
0x180038beb  mov     r11, rdx
0x180038bee  mov     r12, rcx
0x180038bf1  xor     edi, edi
0x180038bf3  mov     [rax-40h], rdi
0x180038bf7  mov     [rax-48h], rdi
0x180038bfb  mov     [rax-50h], edi
0x180038bfe  mov     r14d, edi
0x180038c01  mov     [rax-4Ch], edi
0x180038c04  movzx   esi, di
0x180038c07  mov     [rax-58h], di
0x180038c0b  mov     rdx, [rsp+0E8h+arg_60]
0x180038c13  test    rdx, rdx
0x180038c16  jz      short loc_180038C4F
0x180038c18  lea     r9, [rax-50h]
0x180038c1c  lea     r8, [rax-48h]
0x180038c20  call    ScEncryptPassword
0x180038c25  mov     [rsp+0E8h+var_54], eax
0x180038c2c  test    eax, eax
0x180038c2e  jz      short loc_180038C3F
0x180038c30  mov     ecx, eax; dwErrCode
0x180038c32  call    cs:__imp_SetLastError
0x180038c38  xor     eax, eax
0x180038c3a  jmp     loc_180038F64
0x180038c3f  mov     r10, [rsp+0E8h+arg_10]
0x180038c47  mov     r11, [rsp+0E8h+arg_8]
0x180038c4f  mov     r15, [rsp+0E8h+arg_50]
0x180038c57  test    r15, r15
0x180038c5a  jz      short loc_180038C6E
0x180038c5c  mov     rcx, r15
0x180038c5f  call    ScWStrArraySize
0x180038c64  mov     r14d, eax
0x180038c67  mov     [rsp+0E8h+var_4C], eax
0x180038c6e  mov     rcx, [rsp+0E8h+arg_68]
0x180038c76  test    rcx, rcx
0x180038c79  jz      short loc_180038CA3
0x180038c7b  cmp     byte ptr [rcx], 1
0x180038c7e  jz      short loc_180038C92
0x180038c80  mov     ecx, 57h ; 'W'; dwErrCode
0x180038c85  call    cs:__imp_SetLastError
0x180038c8b  xor     eax, eax
0x180038c8d  jmp     loc_180038F64
0x180038c92  cmp     [rcx+2], di
0x180038c96  cmovnz  si, [rcx+2]
0x180038c9b  mov     [rsp+0E8h+var_58], si
0x180038ca3  test    si, si
0x180038ca6  jz      loc_180038E77
0x180038cac  lea     rax, [rsp+0E8h+var_40]
0x180038cb4  mov     [rsp+0E8h+var_68], rax
0x180038cbc  mov     word ptr [rsp+0E8h+var_70], si
0x180038cc1  mov     eax, [rsp+0E8h+var_50]
0x180038cc8  mov     [rsp+0E8h+var_78], eax
0x180038ccc  mov     rax, [rsp+0E8h+hMem]
0x180038cd4  mov     [rsp+0E8h+var_80], rax
0x180038cd9  mov     rax, [rsp+0E8h+arg_58]
0x180038ce1  mov     [rsp+0E8h+var_88], rax
0x180038ce6  mov     [rsp+0E8h+var_90], r14d
0x180038ceb  mov     [rsp+0E8h+var_98], r15
0x180038cf0  mov     rax, [rsp+0E8h+arg_48]
0x180038cf8  mov     [rsp+0E8h+var_A0], rax
0x180038cfd  mov     rax, [rsp+0E8h+arg_40]
0x180038d05  mov     [rsp+0E8h+var_A8], rax
0x180038d0a  mov     rax, [rsp+0E8h+arg_38]
0x180038d12  mov     [rsp+0E8h+var_B0], rax
0x180038d17  mov     eax, [rsp+0E8h+arg_30]
0x180038d1e  mov     [rsp+0E8h+var_B8], eax
0x180038d22  mov     eax, [rsp+0E8h+arg_28]
0x180038d29  mov     [rsp+0E8h+var_C0], eax
0x180038d2d  mov     eax, [rsp+0E8h+arg_20]
0x180038d34  mov     [rsp+0E8h+var_C8], eax
0x180038d38  mov     r9d, r13d
0x180038d3b  mov     r8, r10
0x180038d3e  mov     rdx, r11
0x180038d41  mov     rcx, r12
0x180038d44  call    RCreateWowService
0x180038d49  mov     ebx, eax
0x180038d4b  mov     [rsp+0E8h+var_54], eax
0x180038d52  jmp     short loc_180038D8C
0x180038d54  mov     ecx, eax; unsigned int
0x180038d56  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180038d5b  mov     ebx, eax
0x180038d5d  mov     [rsp+0E8h+var_54], eax
0x180038d64  mov     r15, [rsp+0E8h+arg_50]
0x180038d6c  mov     r13d, [rsp+0E8h+arg_18]
0x180038d74  mov     r12, [rsp+0E8h+arg_0]
0x180038d7c  mov     r14d, [rsp+0E8h+var_4C]
0x180038d84  movzx   esi, [rsp+0E8h+var_58]
0x180038d8c  cmp     ebx, 78h ; 'x'
0x180038d8f  jnz     loc_180038F39
0x180038d95  mov     eax, 14Ch
0x180038d9a  cmp     si, ax
0x180038d9d  jnz     loc_180038E66
0x180038da3  lea     rax, [rsp+0E8h+var_40]
0x180038dab  mov     [rsp+0E8h+var_70], rax
0x180038db0  mov     eax, [rsp+0E8h+var_50]
0x180038db7  mov     [rsp+0E8h+var_78], eax
0x180038dbb  mov     rax, [rsp+0E8h+hMem]
0x180038dc3  mov     [rsp+0E8h+var_80], rax
0x180038dc8  mov     rax, [rsp+0E8h+arg_58]
0x180038dd0  mov     [rsp+0E8h+var_88], rax
0x180038dd5  mov     [rsp+0E8h+var_90], r14d
0x180038dda  mov     [rsp+0E8h+var_98], r15
0x180038ddf  mov     rax, [rsp+0E8h+arg_48]
0x180038de7  mov     [rsp+0E8h+var_A0], rax
0x180038dec  mov     rax, [rsp+0E8h+arg_40]
0x180038df4  mov     [rsp+0E8h+var_A8], rax
0x180038df9  mov     rax, [rsp+0E8h+arg_38]
0x180038e01  mov     [rsp+0E8h+var_B0], rax
0x180038e06  mov     eax, [rsp+0E8h+arg_30]
0x180038e0d  mov     [rsp+0E8h+var_B8], eax
0x180038e11  mov     eax, [rsp+0E8h+arg_28]
0x180038e18  mov     [rsp+0E8h+var_C0], eax
0x180038e1c  mov     eax, [rsp+0E8h+arg_20]
0x180038e23  mov     [rsp+0E8h+var_C8], eax
0x180038e27  mov     r9d, r13d
0x180038e2a  mov     r8, [rsp+0E8h+arg_10]
0x180038e32  mov     rdx, [rsp+0E8h+arg_8]
0x180038e3a  mov     rcx, r12
0x180038e3d  call    RCreateServiceWOW64W
0x180038e42  mov     ebx, eax
0x180038e44  mov     [rsp+0E8h+var_54], eax
0x180038e4b  jmp     short loc_180038E5D
0x180038e4d  mov     ecx, eax; unsigned int
0x180038e4f  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180038e54  mov     ebx, eax
0x180038e56  mov     [rsp+0E8h+var_54], eax
0x180038e5d  cmp     ebx, 78h ; 'x'
0x180038e60  jnz     loc_180038F27
0x180038e66  mov     ebx, 57h ; 'W'
0x180038e6b  mov     [rsp+0E8h+var_54], ebx
0x180038e72  jmp     loc_180038F27
0x180038e77  lea     rax, [rsp+0E8h+var_40]
0x180038e7f  mov     [rsp+0E8h+var_70], rax
0x180038e84  mov     eax, [rsp+0E8h+var_50]
0x180038e8b  mov     [rsp+0E8h+var_78], eax
0x180038e8f  mov     rax, [rsp+0E8h+hMem]
0x180038e97  mov     [rsp+0E8h+var_80], rax
0x180038e9c  mov     rax, [rsp+0E8h+arg_58]
0x180038ea4  mov     [rsp+0E8h+var_88], rax
0x180038ea9  mov     [rsp+0E8h+var_90], r14d
0x180038eae  mov     [rsp+0E8h+var_98], r15
0x180038eb3  mov     rax, [rsp+0E8h+arg_48]
0x180038ebb  mov     [rsp+0E8h+var_A0], rax
0x180038ec0  mov     rax, [rsp+0E8h+arg_40]
0x180038ec8  mov     [rsp+0E8h+var_A8], rax
0x180038ecd  mov     rax, [rsp+0E8h+arg_38]
0x180038ed5  mov     [rsp+0E8h+var_B0], rax
0x180038eda  mov     eax, [rsp+0E8h+arg_30]
0x180038ee1  mov     [rsp+0E8h+var_B8], eax
0x180038ee5  mov     eax, [rsp+0E8h+arg_28]
0x180038eec  mov     [rsp+0E8h+var_C0], eax
0x180038ef0  mov     eax, [rsp+0E8h+arg_20]
0x180038ef7  mov     [rsp+0E8h+var_C8], eax
0x180038efb  mov     r9d, r13d
0x180038efe  mov     r8, r10
0x180038f01  mov     rdx, r11
0x180038f04  mov     rcx, r12
0x180038f07  call    RCreateServiceW
0x180038f0c  mov     ebx, eax
0x180038f0e  mov     [rsp+0E8h+var_54], eax
0x180038f15  jmp     short loc_180038F27
0x180038f17  mov     ecx, eax; unsigned int
0x180038f19  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180038f1e  mov     ebx, eax
0x180038f20  mov     [rsp+0E8h+var_54], eax
0x180038f27  jmp     short loc_180038F39
0x180038f29  mov     ecx, eax; unsigned int
0x180038f2b  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180038f30  mov     ebx, eax
0x180038f32  mov     [rsp+0E8h+var_54], eax
0x180038f39  mov     rcx, [rsp+0E8h+hMem]; hMem
0x180038f41  test    rcx, rcx
0x180038f44  jz      short loc_180038F4C
0x180038f46  call    cs:__imp_LocalFree
0x180038f4c  test    ebx, ebx
0x180038f4e  jz      short loc_180038F5C
0x180038f50  mov     ecx, ebx; dwErrCode
0x180038f52  call    cs:__imp_SetLastError
0x180038f58  xor     eax, eax
0x180038f5a  jmp     short loc_180038F64
0x180038f5c  mov     rax, [rsp+0E8h+var_40]
0x180038f64  add     rsp, 0B0h
0x180038f6b  pop     r15
0x180038f6d  pop     r14
0x180038f6f  pop     r13
0x180038f71  pop     r12
0x180038f73  pop     rdi
0x180038f74  pop     rsi
0x180038f75  pop     rbx
0x180038f76  retn
0x180050562  push    rbp
0x180050564  sub     rsp, 90h
0x18005056b  mov     rbp, rdx
0x18005056e  mov     rcx, [rcx]
0x180050571  mov     ecx, [rcx]; ExceptionCode
0x180050573  call    cs:__imp_I_RpcExceptionFilter
0x180050579  nop
0x18005057a  add     rsp, 90h
0x180050581  pop     rbp
0x180050582  retn
0x180050584  push    rbp
0x180050586  sub     rsp, 90h
0x18005058d  mov     rbp, rdx
0x180050590  mov     rcx, [rcx]
0x180050593  mov     ecx, [rcx]; ExceptionCode
0x180050595  call    cs:__imp_I_RpcExceptionFilter
0x18005059b  nop
0x18005059c  add     rsp, 90h
0x1800505a3  pop     rbp
0x1800505a4  retn
0x1800505a6  push    rbp
0x1800505a8  sub     rsp, 90h
0x1800505af  mov     rbp, rdx
0x1800505b2  mov     rcx, [rcx]
0x1800505b5  mov     ecx, [rcx]; ExceptionCode
0x1800505b7  call    cs:__imp_I_RpcExceptionFilter
0x1800505bd  nop
0x1800505be  add     rsp, 90h
0x1800505c5  pop     rbp
0x1800505c6  retn
0x1800505c8  push    rbp
0x1800505ca  sub     rsp, 90h
0x1800505d1  mov     rbp, rdx
0x1800505d4  mov     rcx, [rcx]
0x1800505d7  mov     ecx, [rcx]; ExceptionCode
0x1800505d9  call    cs:__imp_I_RpcExceptionFilter
0x1800505df  nop
0x1800505e0  add     rsp, 90h
0x1800505e7  pop     rbp
0x1800505e8  retn
```
