# CRpcHandler::SetSecurity(CRegEndpoint *,void *,ulong)

- ea: `0x180005df0`
- end: `0x180005eb6`
- name: `?SetSecurity@CRpcHandler@@QEAAKPEAVCRegEndpoint@@PEAXK@Z`
- size: `198`
- prototype: `unsigned int(CRpcHandler *__hidden this, struct CRegEndpoint *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011ec0`

## callees

- `0x180003944`
- `0x180005df0`
- `0x180015d60`

## pseudocode

```c
__int64 __fastcall CRpcHandler::SetSecurity(CRpcHandler *this, struct CRegEndpoint *a2, void *a3, int a4)
{
  __int64 v4; // rax
  char *v5; // rcx
  _BYTE *v6; // r10
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  _BYTE v18[1064]; // [rsp+20h] [rbp-428h] BYREF

  v4 = 8;
  v5 = (char *)a2 + 72;
  v6 = v18;
  do
  {
    v7 = *((_OWORD *)v5 + 1);
    *(_OWORD *)v6 = *(_OWORD *)v5;
    v8 = *((_OWORD *)v5 + 2);
    *((_OWORD *)v6 + 1) = v7;
    v9 = *((_OWORD *)v5 + 3);
    *((_OWORD *)v6 + 2) = v8;
    v10 = *((_OWORD *)v5 + 4);
    *((_OWORD *)v6 + 3) = v9;
    v11 = *((_OWORD *)v5 + 5);
    *((_OWORD *)v6 + 4) = v10;
    v12 = *((_OWORD *)v5 + 6);
    *((_OWORD *)v6 + 5) = v11;
    v13 = *((_OWORD *)v5 + 7);
    v5 += 128;
    *((_OWORD *)v6 + 6) = v12;
    v6 += 128;
    *((_OWORD *)v6 - 1) = v13;
    --v4;
  }
  while ( v4 );
  v14 = *((_QWORD *)v5 + 2);
  *(_OWORD *)v6 = *(_OWORD *)v5;
  *((_QWORD *)v6 + 2) = v14;
  *((_DWORD *)v6 + 6) = *((_DWORD *)v5 + 6);
  if ( (v18[8] & 1) != 0 )
  {
    v15 = CRegRpcEndpoint::SetSecurity(a2, a3, a4);
    ElValidateWin32(v15, v16, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 684);
  }
  else
  {
    return 50;
  }
  return v15;
}

```

## disassembly

```asm
0x180005df0  push    rbx
0x180005df2  sub     rsp, 440h
0x180005df9  mov     eax, 8
0x180005dfe  lea     rcx, [rdx+48h]
0x180005e02  mov     r11, rdx
0x180005e05  lea     r10, [rsp+448h+var_428]
0x180005e0a  mov     rbx, r8
0x180005e0d  lea     edx, [rax+78h]
0x180005e10  movups  xmm0, xmmword ptr [rcx]
0x180005e13  movups  xmm1, xmmword ptr [rcx+10h]
0x180005e17  movups  xmmword ptr [r10], xmm0
0x180005e1b  movups  xmm0, xmmword ptr [rcx+20h]
0x180005e1f  movups  xmmword ptr [r10+10h], xmm1
0x180005e24  movups  xmm1, xmmword ptr [rcx+30h]
0x180005e28  movups  xmmword ptr [r10+20h], xmm0
0x180005e2d  movups  xmm0, xmmword ptr [rcx+40h]
0x180005e31  movups  xmmword ptr [r10+30h], xmm1
0x180005e36  movups  xmm1, xmmword ptr [rcx+50h]
0x180005e3a  movups  xmmword ptr [r10+40h], xmm0
0x180005e3f  movups  xmm0, xmmword ptr [rcx+60h]
0x180005e43  movups  xmmword ptr [r10+50h], xmm1
0x180005e48  movups  xmm1, xmmword ptr [rcx+70h]
0x180005e4c  add     rcx, rdx
0x180005e4f  movups  xmmword ptr [r10+60h], xmm0
0x180005e54  add     r10, rdx
0x180005e57  movups  xmmword ptr [r10-10h], xmm1
0x180005e5c  sub     rax, 1
0x180005e60  jnz     short loc_180005E10
0x180005e62  mov     rax, [rcx+10h]
0x180005e66  movups  xmm0, xmmword ptr [rcx]
0x180005e69  movups  xmmword ptr [r10], xmm0
0x180005e6d  mov     [r10+10h], rax
0x180005e71  mov     eax, [rcx+18h]
0x180005e74  mov     [r10+18h], eax
0x180005e78  test    [rsp+448h+var_420], 1
0x180005e7d  jnz     short loc_180005E86
0x180005e7f  mov     ebx, 32h ; '2'
0x180005e84  jmp     short loc_180005EAA
0x180005e86  mov     r8d, r9d; unsigned int
0x180005e89  mov     rdx, rbx; void *
0x180005e8c  mov     rcx, r11; this
0x180005e8f  call    ?SetSecurity@CRegRpcEndpoint@@QEAAKPEAXK@Z; CRegRpcEndpoint::SetSecurity(void *,ulong)
0x180005e94  mov     r9d, 2ACh
0x180005e9a  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180005ea1  mov     ecx, eax
0x180005ea3  mov     ebx, eax
0x180005ea5  call    ElValidateWin32
0x180005eaa  mov     eax, ebx
0x180005eac  add     rsp, 440h
0x180005eb3  pop     rbx
0x180005eb4  retn
```
