# CXMLLogFormatter::Process(ILogContext *)

- ea: `0x180024de0`
- end: `0x180024f7e`
- name: `?Process@CXMLLogFormatter@@UEAA?AW4tagLOGRESULT@@PEAVILogContext@@@Z`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18002309c`
- `0x180023204`
- `0x180023380`
- `0x18002365c`
- `0x180024de0`
- `0x180024fd0`
- `0x18002a010`

## pseudocode

```c
_BOOL8 __fastcall CXMLLogFormatter::Process(__int64 a1, __int64 *a2)
{
  __int64 v3; // rax
  int v4; // r14d
  unsigned int v5; // esi
  unsigned int v6; // r15d
  __int64 v7; // rax
  __int64 v8; // rbx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // ebx
  unsigned int v15; // esi
  wchar_t *v16; // r14
  __int64 *v18; // [rsp+20h] [rbp-40h] BYREF
  int v19; // [rsp+28h] [rbp-38h]
  __int64 v20; // [rsp+2Ch] [rbp-34h]
  const char *v21; // [rsp+38h] [rbp-28h]
  const char *v22; // [rsp+40h] [rbp-20h]
  __int128 v23; // [rsp+48h] [rbp-18h]
  unsigned int v24; // [rsp+98h] [rbp+38h] BYREF

  v18 = a2;
  v20 = 0;
  v21 = "<z:row";
  v22 = "/>\n";
  v3 = *a2;
  v4 = 0;
  v23 = 0;
  v5 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *))(v3 + 56))(a2);
  if ( v6 )
  {
    do
    {
      v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a2 + 48))(a2, v5);
      v8 = v7;
      v24 = 0;
      v9 = *(_DWORD *)(v7 + 520);
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 == 1 )
              v12 = 19;
            else
              v12 = 0;
          }
          else
          {
            v12 = 2 * *(_DWORD *)(v7 + 536);
          }
        }
        else
        {
          v12 = 11;
        }
      }
      else
      {
        CXMLLogFormatter::EscapeXML(0, *(const unsigned __int16 **)(v7 + 528), &v24);
        v12 = v24;
      }
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v8 + 2 * v13) );
      v4 += v13 + v12 + 4;
      ++v5;
    }
    while ( v5 < v6 );
  }
  v19 = v4 + 2;
  if ( !(unsigned int)CLogEntryBuilder::BeginEntry((CLogEntryBuilder *)&v18) )
    return 0;
  v14 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 56))(a2);
  while ( v14 < v15 )
  {
    v16 = (wchar_t *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a2 + 48))(a2, v14);
    if ( !CLogEntryBuilder::Printf((CLogEntryBuilder *)&v18, " %S=\"", v16)
      || !(unsigned int)CXMLLogFormatter::WriteField((struct CLogEntryBuilder *)&v18, (struct tagLOG_FIELD_VALUE *)v16)
      || !CLogEntryBuilder::Printf((CLogEntryBuilder *)&v18, "\"") )
    {
      return 0;
    }
    ++v14;
  }
  return (unsigned int)CLogEntryBuilder::EndEntry((CLogEntryBuilder *)&v18) != 0;
}

```

## disassembly

```asm
0x180024de0  mov     [rsp-28h+arg_0], rbx
0x180024de5  mov     [rsp-28h+arg_10], rsi
0x180024dea  push    rbp
0x180024deb  push    rdi
0x180024dec  push    r12
0x180024dee  push    r14
0x180024df0  push    r15
0x180024df2  mov     rbp, rsp
0x180024df5  sub     rsp, 60h
0x180024df9  xor     r12d, r12d
0x180024dfc  mov     [rbp+var_40], rdx
0x180024e00  lea     rax, aZRow; "<z:row"
0x180024e07  mov     [rbp+var_34], r12
0x180024e0b  mov     [rbp+var_28], rax
0x180024e0f  xorps   xmm0, xmm0
0x180024e12  lea     rax, asc_1800335B8; "/>\n"
0x180024e19  mov     rcx, rdx
0x180024e1c  mov     [rbp+var_20], rax
0x180024e20  mov     rdi, rdx
0x180024e23  mov     rax, [rdx]
0x180024e26  mov     r14d, r12d
0x180024e29  movdqu  [rbp+var_18], xmm0
0x180024e2e  mov     esi, r12d
0x180024e31  mov     rax, [rax+38h]
0x180024e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e3a  mov     r15d, eax
0x180024e3d  test    eax, eax
0x180024e3f  jz      loc_180024ECA
0x180024e45  mov     rcx, [rdi]
0x180024e48  mov     edx, esi
0x180024e4a  mov     rax, [rcx+30h]
0x180024e4e  mov     rcx, rdi
0x180024e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e56  mov     rbx, rax
0x180024e59  mov     [rbp+arg_8], r12d
0x180024e5d  mov     edx, [rax+208h]
0x180024e63  test    edx, edx
0x180024e65  jz      short loc_180024E93
0x180024e67  sub     edx, 1
0x180024e6a  jz      short loc_180024E8C
0x180024e6c  sub     edx, 1
0x180024e6f  jz      short loc_180024E82
0x180024e71  cmp     edx, 1
0x180024e74  jz      short loc_180024E7B
0x180024e76  mov     eax, r12d
0x180024e79  jmp     short loc_180024EA8
0x180024e7b  mov     eax, 13h
0x180024e80  jmp     short loc_180024EA8
0x180024e82  mov     eax, [rax+218h]
0x180024e88  add     eax, eax
0x180024e8a  jmp     short loc_180024EA8
0x180024e8c  mov     eax, 0Bh
0x180024e91  jmp     short loc_180024EA8
0x180024e93  mov     rdx, [rax+210h]; unsigned __int16 *
0x180024e9a  lea     r8, [rbp+arg_8]; unsigned int *
0x180024e9e  xor     ecx, ecx; this
0x180024ea0  call    ?EscapeXML@CXMLLogFormatter@@CAHPEAVCLogEntryBuilder@@PEBGPEAI@Z; CXMLLogFormatter::EscapeXML(CLogEntryBuilder *,ushort const *,uint *)
0x180024ea5  mov     eax, [rbp+arg_8]
0x180024ea8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024eac  inc     rcx
0x180024eaf  cmp     [rbx+rcx*2], r12w
0x180024eb4  jnz     short loc_180024EAC
0x180024eb6  add     eax, ecx
0x180024eb8  add     r14d, 4
0x180024ebc  add     r14d, eax
0x180024ebf  inc     esi
0x180024ec1  cmp     esi, r15d
0x180024ec4  jb      loc_180024E45
0x180024eca  lea     eax, [r14+2]
0x180024ece  lea     rcx, [rbp+var_40]; this
0x180024ed2  mov     [rbp+var_38], eax
0x180024ed5  call    ?BeginEntry@CLogEntryBuilder@@QEAAHXZ; CLogEntryBuilder::BeginEntry(void)
0x180024eda  test    eax, eax
0x180024edc  jz      loc_180024F62
0x180024ee2  mov     rax, [rdi]
0x180024ee5  mov     rcx, rdi
0x180024ee8  mov     ebx, r12d
0x180024eeb  mov     rax, [rax+38h]
0x180024eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ef4  mov     esi, eax
0x180024ef6  cmp     ebx, esi
0x180024ef8  jnb     short loc_180024F4D
0x180024efa  mov     rcx, [rdi]
0x180024efd  mov     edx, ebx
0x180024eff  mov     rax, [rcx+30h]
0x180024f03  mov     rcx, rdi
0x180024f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f0b  mov     r8, rax
0x180024f0e  lea     rdx, aS_2; " %S=\""
0x180024f15  lea     rcx, [rbp+var_40]; this
0x180024f19  mov     r14, rax
0x180024f1c  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x180024f21  test    eax, eax
0x180024f23  jz      short loc_180024F62
0x180024f25  mov     rdx, r14; struct tagLOG_FIELD_VALUE *
0x180024f28  lea     rcx, [rbp+var_40]; this
0x180024f2c  call    ?WriteField@CXMLLogFormatter@@CAHPEAVCLogEntryBuilder@@PEAUtagLOG_FIELD_VALUE@@@Z; CXMLLogFormatter::WriteField(CLogEntryBuilder *,tagLOG_FIELD_VALUE *)
0x180024f31  test    eax, eax
0x180024f33  jz      short loc_180024F62
0x180024f35  lea     rdx, asc_1800335CC; "\""
0x180024f3c  lea     rcx, [rbp+var_40]; this
0x180024f40  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x180024f45  test    eax, eax
0x180024f47  jz      short loc_180024F62
0x180024f49  inc     ebx
0x180024f4b  jmp     short loc_180024EF6
0x180024f4d  lea     rcx, [rbp+var_40]; this
0x180024f51  call    ?EndEntry@CLogEntryBuilder@@QEAAHXZ; CLogEntryBuilder::EndEntry(void)
0x180024f56  test    eax, eax
0x180024f58  mov     ecx, r12d
0x180024f5b  setnz   cl
0x180024f5e  mov     eax, ecx
0x180024f60  jmp     short loc_180024F64
0x180024f62  xor     eax, eax
0x180024f64  lea     r11, [rsp+60h+var_s0]
0x180024f69  mov     rbx, [r11+30h]
0x180024f6d  mov     rsi, [r11+40h]
0x180024f71  mov     rsp, r11
0x180024f74  pop     r15
0x180024f76  pop     r14
0x180024f78  pop     r12
0x180024f7a  pop     rdi
0x180024f7b  pop     rbp
0x180024f7c  retn
```
