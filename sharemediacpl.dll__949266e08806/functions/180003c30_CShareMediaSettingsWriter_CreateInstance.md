# CShareMediaSettingsWriter_CreateInstance

- ea: `0x180003c30`
- end: `0x180003d56`
- name: `CShareMediaSettingsWriter_CreateInstance`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180001914`
- `0x180003254`
- `0x180003860`
- `0x180003888`
- `0x180003c30`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriter_CreateInstance(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rbx
  unsigned int v4; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_13d719e44d5638f61d35bd3924991706_Traceguids);
  v3 = operator new(0x10u);
  if ( v3 )
  {
    v3[2] = 1;
    *(_QWORD *)v3 = &CShareMediaSettingsWriterImpl::`vftable';
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
    DllAddRef();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
    v4 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64))v3)(v3, &GUID_00000000_0000_0000_c000_000000000046, a2);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  else
  {
    v4 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_13d719e44d5638f61d35bd3924991706_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180003c30  mov     [rsp+arg_0], rbx
0x180003c35  mov     [rsp+arg_8], rbp
0x180003c3a  push    rdi
0x180003c3b  sub     rsp, 20h
0x180003c3f  mov     rdi, rdx
0x180003c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c49  lea     rbp, WPP_GLOBAL_Control
0x180003c50  cmp     rcx, rbp
0x180003c53  jz      short loc_180003C70
0x180003c55  test    byte ptr [rcx+1Ch], 20h
0x180003c59  jz      short loc_180003C70
0x180003c5b  mov     rcx, [rcx+10h]
0x180003c5f  lea     r8, WPP_13d719e44d5638f61d35bd3924991706_Traceguids
0x180003c66  mov     edx, 0Ch
0x180003c6b  call    WPP_SF_
0x180003c70  mov     ecx, 10h; Size
0x180003c75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c7a  mov     rbx, rax
0x180003c7d  test    rax, rax
0x180003c80  jz      loc_180003D15
0x180003c86  lea     rax, ??_7CShareMediaSettingsWriterImpl@@6B@; const CShareMediaSettingsWriterImpl::`vftable'
0x180003c8d  mov     dword ptr [rbx+8], 1
0x180003c94  mov     [rbx], rax
0x180003c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c9e  cmp     rcx, rbp
0x180003ca1  jz      short loc_180003CBE
0x180003ca3  test    byte ptr [rcx+1Ch], 20h
0x180003ca7  jz      short loc_180003CBE
0x180003ca9  mov     rcx, [rcx+10h]
0x180003cad  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180003cb4  mov     edx, 0Ah
0x180003cb9  call    WPP_SF_
0x180003cbe  call    DllAddRef
0x180003cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cca  cmp     rcx, rbp
0x180003ccd  jz      short loc_180003CEA
0x180003ccf  test    byte ptr [rcx+1Ch], 20h
0x180003cd3  jz      short loc_180003CEA
0x180003cd5  mov     rcx, [rcx+10h]
0x180003cd9  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180003ce0  mov     edx, 0Bh
0x180003ce5  call    WPP_SF_
0x180003cea  mov     rax, [rbx]
0x180003ced  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003cf4  mov     r8, rdi
0x180003cf7  mov     rcx, rbx
0x180003cfa  mov     rax, [rax]
0x180003cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d02  mov     rcx, [rbx]
0x180003d05  mov     edi, eax
0x180003d07  mov     rax, [rcx+10h]
0x180003d0b  mov     rcx, rbx
0x180003d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d13  jmp     short loc_180003D1A
0x180003d15  mov     edi, 8007000Eh
0x180003d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d21  cmp     rcx, rbp
0x180003d24  jz      short loc_180003D44
0x180003d26  test    byte ptr [rcx+1Ch], 20h
0x180003d2a  jz      short loc_180003D44
0x180003d2c  mov     rcx, [rcx+10h]
0x180003d30  lea     r8, WPP_13d719e44d5638f61d35bd3924991706_Traceguids
0x180003d37  mov     edx, 0Dh
0x180003d3c  mov     r9d, edi
0x180003d3f  call    WPP_SF_d
0x180003d44  mov     rbx, [rsp+28h+arg_0]
0x180003d49  mov     eax, edi
0x180003d4b  mov     rbp, [rsp+28h+arg_8]
0x180003d50  add     rsp, 20h
0x180003d54  pop     rdi
0x180003d55  retn
```
