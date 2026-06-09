# LGetProxyStatus

- ea: `0x18000f6a0`
- end: `0x18000f8eb`
- name: `LGetProxyStatus`
- size: `587`
- prototype: `_UNKNOWN **__fastcall(int, _DWORD *, unsigned int, unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x1800070e8`
- `0x18000f6a0`
- `0x180017b74`
- `0x180019fcc`
- `0x18003dc84`
- `0x180040010`

## string_xrefs

- `0x18000f8a4`: `lineGetProxyStatus - no line open`

## pseudocode

```c
_UNKNOWN **__fastcall LGetProxyStatus(int a1, _DWORD *a2, unsigned int a3, unsigned int *a4, _DWORD *a5)
{
  _UNKNOWN **result; // rax
  int v8; // eax
  unsigned int v9; // r10d
  unsigned int v10; // esi
  __int64 v11; // r11
  unsigned int v12; // ecx
  unsigned int i; // edx
  unsigned int *v14; // r8
  unsigned int j; // edx
  __int64 v16; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v17; // [rsp+78h] [rbp-40h]
  __int64 v18; // [rsp+80h] [rbp-38h] BYREF
  HANDLE TargetHandle[6]; // [rsp+88h] [rbp-30h] BYREF
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+0h] BYREF
  int v21; // [rsp+D0h] [rbp+18h] BYREF

  result = &retaddr;
  v21 = 0;
  TargetHandle[0] = 0;
  v16 = 0;
  v18 = 0;
  if ( a2[5] > a3 )
  {
    *a2 = -2147483576;
    return result;
  }
  if ( a2[4] != 65539
    && a2[4] != 65540
    && a2[4] != 0x20000
    && a2[4] != 131073
    && a2[4] != 131074
    && (unsigned int)(a2[4] - 196608) >= 2 )
  {
    *a2 = -2147483636;
    return result;
  }
  v8 = LineProlog(
         a1,
         3,
         a2[2],
         (int)&v21,
         a2[3],
         TargetHandle,
         (__int64)&v16 + 4,
         0,
         0,
         0,
         0,
         (__int64)&v16,
         (__int64)&v18);
  *a2 = v8;
  if ( !v8 )
  {
    v9 = a2[5];
    if ( v9 >= 0x18 )
    {
      v10 = a2[4];
      if ( *(_DWORD *)(v18 + 36) )
      {
        InitTapiStruct(a4, v9, 0x18u, 1);
        *a2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(pRemoteSP + 1168))((unsigned int)v21, v10, a4);
LABEL_14:
        a2[6] = v10;
        a2[5] = 0;
        *a5 = a4[2] + 60;
        return (_UNKNOWN **)LineEpilogSync(a2, TargetHandle[0], HIDWORD(v16), (unsigned int)v16);
      }
      v11 = *(_QWORD *)(v18 + 8);
      if ( !v11 )
      {
        *a2 = -2147483576;
        TRACELogPrint(65538, "lineGetProxyStatus - no line open");
        return (_UNKNOWN **)LineEpilogSync(a2, TargetHandle[0], HIDWORD(v16), (unsigned int)v16);
      }
      v12 = 24;
      a4[3] = 0;
      for ( i = 1; i <= 0x14; ++i )
      {
        if ( *(_QWORD *)(v11 + 8LL * i + 24) )
        {
          v12 += 4;
          v17 = v12;
        }
      }
      if ( v9 >= v12 )
      {
        *(_QWORD *)(a4 + 3) = 0;
        a4[5] = 24;
        v14 = a4 + 6;
        for ( j = 1; j <= 0x14; ++j )
        {
          if ( *(_QWORD *)(v11 + 8LL * j + 24) )
          {
            a4[4] += 4;
            ++a4[3];
            *v14++ = j;
            TargetHandle[1] = v14;
          }
        }
        *a4 = v9;
        a4[2] = v12;
        a4[1] = v12;
        goto LABEL_14;
      }
    }
    *a2 = -2147483571;
  }
  return (_UNKNOWN **)LineEpilogSync(a2, TargetHandle[0], HIDWORD(v16), (unsigned int)v16);
}

```

## disassembly

```asm
0x18000f6a0  mov     rax, rsp
0x18000f6a3  mov     [rax+8], rbx
0x18000f6a7  mov     [rax+10h], rdx
0x18000f6ab  push    rsi
0x18000f6ac  push    rdi
0x18000f6ad  push    r14
0x18000f6af  sub     rsp, 0A0h
0x18000f6b6  mov     rdi, r9
0x18000f6b9  mov     rbx, rdx
0x18000f6bc  mov     r10, rcx
0x18000f6bf  xor     r14d, r14d
0x18000f6c2  mov     [rax-44h], r14d
0x18000f6c6  mov     [rax+18h], r14d
0x18000f6ca  mov     [rax-30h], r14
0x18000f6ce  mov     [rax-48h], r14d
0x18000f6d2  mov     [rax-38h], r14
0x18000f6d6  cmp     [rdx+14h], r8d
0x18000f6da  jbe     short loc_18000F6E7
0x18000f6dc  mov     dword ptr [rdx], 80000048h
0x18000f6e2  jmp     loc_18000F8D7
0x18000f6e7  mov     ecx, [rdx+10h]
0x18000f6ea  sub     ecx, 10003h
0x18000f6f0  jz      short loc_18000F721
0x18000f6f2  sub     ecx, 1
0x18000f6f5  jz      short loc_18000F721
0x18000f6f7  sub     ecx, 0FFFCh
0x18000f6fd  jz      short loc_18000F721
0x18000f6ff  sub     ecx, 1
0x18000f702  jz      short loc_18000F721
0x18000f704  sub     ecx, 1
0x18000f707  jz      short loc_18000F721
0x18000f709  sub     ecx, 0FFFEh
0x18000f70f  jz      short loc_18000F721
0x18000f711  cmp     ecx, 1
0x18000f714  jz      short loc_18000F721
0x18000f716  mov     dword ptr [rdx], 8000000Ch
0x18000f71c  jmp     loc_18000F8D7
0x18000f721  lea     rax, [rsp+0B8h+var_38]
0x18000f729  mov     [rsp+0B8h+var_58], rax; __int64
0x18000f72e  lea     rax, [rsp+0B8h+var_48]
0x18000f733  mov     [rsp+0B8h+var_60], rax; __int64
0x18000f738  mov     [rsp+0B8h+var_68], r14d; int
0x18000f73d  mov     [rsp+0B8h+var_70], r14; __int64
0x18000f742  mov     [rsp+0B8h+var_78], r14; __int64
0x18000f747  mov     [rsp+0B8h+var_80], r14d; int
0x18000f74c  lea     rax, [rsp+0B8h+var_48+4]
0x18000f751  mov     [rsp+0B8h+var_88], rax; __int64
0x18000f756  lea     rax, [rsp+0B8h+TargetHandle]
0x18000f75e  mov     [rsp+0B8h+lpTargetHandle], rax; lpTargetHandle
0x18000f763  mov     eax, [rdx+0Ch]
0x18000f766  mov     [rsp+0B8h+var_98], eax; int
0x18000f76a  lea     r9, [rsp+0B8h+arg_10]; int
0x18000f772  mov     r8d, [rdx+8]; int
0x18000f776  mov     edx, 3; int
0x18000f77b  mov     rcx, r10; int
0x18000f77e  call    LineProlog
0x18000f783  mov     [rbx], eax
0x18000f785  test    eax, eax
0x18000f787  jnz     loc_18000F8BD
0x18000f78d  mov     r10d, [rbx+14h]
0x18000f791  lea     r8d, [rax+18h]
0x18000f795  cmp     r10d, r8d
0x18000f798  jb      loc_18000F8B7
0x18000f79e  mov     esi, [rbx+10h]
0x18000f7a1  mov     rax, [rsp+0B8h+var_38]
0x18000f7a9  cmp     [rax+24h], r14d
0x18000f7ad  jz      short loc_18000F7FB
0x18000f7af  lea     r9d, [r8-17h]
0x18000f7b3  mov     edx, r10d
0x18000f7b6  mov     rcx, rdi
0x18000f7b9  call    InitTapiStruct
0x18000f7be  mov     rax, cs:pRemoteSP
0x18000f7c5  mov     r8, rdi
0x18000f7c8  mov     edx, esi
0x18000f7ca  mov     ecx, [rsp+0B8h+arg_10]
0x18000f7d1  mov     rax, [rax+490h]
0x18000f7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7dd  mov     [rbx], eax
0x18000f7df  mov     [rbx+18h], esi
0x18000f7e2  mov     [rbx+14h], r14d
0x18000f7e6  mov     ecx, [rdi+8]
0x18000f7e9  add     ecx, 3Ch ; '<'
0x18000f7ec  mov     rax, [rsp+0B8h+arg_20]
0x18000f7f4  mov     [rax], ecx
0x18000f7f6  jmp     loc_18000F8BD
0x18000f7fb  mov     r11, [rax+8]
0x18000f7ff  test    r11, r11
0x18000f802  jz      loc_18000F89E
0x18000f808  mov     ecx, r8d
0x18000f80b  mov     [rdi+0Ch], r14d
0x18000f80f  mov     r9d, 1
0x18000f815  mov     edx, r9d
0x18000f818  cmp     edx, 14h
0x18000f81b  ja      short loc_18000F842
0x18000f81d  mov     eax, edx
0x18000f81f  cmp     [r11+rax*8+18h], r14
0x18000f824  jz      short loc_18000F82D
0x18000f826  add     ecx, 4
0x18000f829  mov     [rsp+0B8h+var_40], ecx
0x18000f82d  add     edx, r9d
0x18000f830  jmp     short loc_18000F818
0x18000f832  mov     rbx, [rsp+0B8h+arg_8]
0x18000f83a  mov     dword ptr [rbx], 80000049h
0x18000f840  jmp     short loc_18000F8BD
0x18000f842  cmp     r10d, ecx
0x18000f845  jb      short loc_18000F8B7
0x18000f847  mov     [rdi+0Ch], r14
0x18000f84b  mov     [rdi+14h], r8d
0x18000f84f  lea     r8, [rdi+18h]
0x18000f853  mov     edx, r9d
0x18000f856  cmp     edx, 14h
0x18000f859  ja      short loc_18000F890
0x18000f85b  mov     eax, edx
0x18000f85d  cmp     [r11+rax*8+18h], r14
0x18000f862  jz      short loc_18000F87B
0x18000f864  add     dword ptr [rdi+10h], 4
0x18000f868  add     [rdi+0Ch], r9d
0x18000f86c  mov     [r8], edx
0x18000f86f  add     r8, 4
0x18000f873  mov     [rsp+0B8h+var_28], r8
0x18000f87b  add     edx, r9d
0x18000f87e  jmp     short loc_18000F856
0x18000f880  mov     rbx, [rsp+0B8h+arg_8]
0x18000f888  mov     dword ptr [rbx], 80000049h
0x18000f88e  jmp     short loc_18000F8BD
0x18000f890  mov     [rdi], r10d
0x18000f893  mov     [rdi+8], ecx
0x18000f896  mov     [rdi+4], ecx
0x18000f899  jmp     loc_18000F7DF
0x18000f89e  mov     dword ptr [rbx], 80000048h
0x18000f8a4  lea     rdx, aLinegetproxyst; "lineGetProxyStatus - no line open"
0x18000f8ab  mov     ecx, 10002h
0x18000f8b0  call    TRACELogPrint
0x18000f8b5  jmp     short loc_18000F8BD
0x18000f8b7  mov     dword ptr [rbx], 8000004Dh
0x18000f8bd  mov     r9d, dword ptr [rsp+0B8h+var_48]
0x18000f8c2  mov     r8d, dword ptr [rsp+0B8h+var_48+4]
0x18000f8c7  mov     rdx, [rsp+0B8h+TargetHandle]
0x18000f8cf  mov     rcx, rbx
0x18000f8d2  call    LineEpilogSync
0x18000f8d7  mov     rbx, [rsp+0B8h+arg_0]
0x18000f8df  add     rsp, 0A0h
0x18000f8e6  pop     r14
0x18000f8e8  pop     rdi
0x18000f8e9  pop     rsi
0x18000f8ea  retn
```
