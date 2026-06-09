# ClCertRegConcatKeyToPath

- ea: `0x180038e94`
- end: `0x180038fe7`
- name: `ClCertRegConcatKeyToPath`
- size: `339`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x180036fb8`
- `0x180039214`
- `0x1800395a4`

## callees

- `0x180020dc0`
- `0x180026e5c`
- `0x180038d98`
- `0x180038e94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180038f84`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180038f84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038ec1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038ec1`

## string_xrefs

- `0x180038f07`: `System\CurrentControlSet\Services\LanmanServer\CertsAcl\`
- `0x180038f24`: `System\CurrentControlSet\Services\LanmanServer\CertsAcl\`

## pseudocode

```c
__int64 __fastcall ClCertRegConcatKeyToPath(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rax
  __int64 v6; // rdi
  _OWORD *v7; // rax
  void *v8; // rbx
  unsigned int v9; // edi

  *a3 = 0;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a2 + 2 * v4) );
  v6 = v4 + 57;
  v7 = LocalAlloc(0, 2 * (v4 + 57));
  v8 = v7;
  if ( v7 )
  {
    *v7 = *(_OWORD *)L"System\\CurrentControlSet\\Services\\LanmanServer\\CertsAcl\\";
    v7[1] = *(_OWORD *)L"urrentControlSet\\Services\\LanmanServer\\CertsAcl\\";
    v7[2] = *(_OWORD *)L"ntrolSet\\Services\\LanmanServer\\CertsAcl\\";
    v7[3] = *(_OWORD *)L"\\Services\\LanmanServer\\CertsAcl\\";
    v7[4] = *(_OWORD *)L"s\\LanmanServer\\CertsAcl\\";
    v7[5] = *(_OWORD *)L"Server\\CertsAcl\\";
    v7[6] = *(_OWORD *)L"ertsAcl\\";
    *((_WORD *)v7 + 56) = aSystemCurrentc_6[56];
    if ( (unsigned int)_o_wcscat_s(v7, v6, a2) )
    {
      v9 = 122;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_053b19d310c5352633ee666709ba12ba_Traceguids);
      }
    }
    else
    {
      *a3 = v8;
      v9 = 0;
      v8 = 0;
    }
  }
  else
  {
    v9 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
        (unsigned int)L"System\\CurrentControlSet\\Services\\LanmanServer\\CertsAcl\\",
        a2);
    }
  }
  ClCertLocalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x180038e94  push    rbx
0x180038e96  push    rbp
0x180038e97  push    rsi
0x180038e98  push    rdi
0x180038e99  push    r14
0x180038e9b  sub     rsp, 30h
0x180038e9f  xor     ebp, ebp
0x180038ea1  mov     r14, r8
0x180038ea4  mov     [r8], rbp
0x180038ea7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038eab  mov     rsi, rdx
0x180038eae  inc     rax
0x180038eb1  cmp     [rdx+rax*2], bp
0x180038eb5  jnz     short loc_180038EAE
0x180038eb7  lea     rdi, [rax+39h]
0x180038ebb  xor     ecx, ecx; uFlags
0x180038ebd  lea     rdx, [rdi+rdi]; uBytes
0x180038ec1  call    cs:__imp_LocalAlloc
0x180038ec7  mov     rbx, rax
0x180038eca  test    rax, rax
0x180038ecd  jnz     short loc_180038F24
0x180038ecf  lea     edi, [rax+8]
0x180038ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ed9  lea     rax, WPP_GLOBAL_Control
0x180038ee0  cmp     rcx, rax
0x180038ee3  jz      loc_180038FD2
0x180038ee9  test    dword ptr [rcx+1Ch], 800h
0x180038ef0  jz      loc_180038FD2
0x180038ef6  cmp     byte ptr [rcx+19h], 1
0x180038efa  jb      loc_180038FD2
0x180038f00  mov     rcx, [rcx+10h]
0x180038f04  lea     edx, [rbx+5Bh]
0x180038f07  lea     r9, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\La"...
0x180038f0e  mov     [rsp+58h+var_38], rsi
0x180038f13  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180038f1a  call    WPP_SF_SS
0x180038f1f  jmp     loc_180038FD2
0x180038f24  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\La"...
0x180038f2b  mov     r8, rsi
0x180038f2e  movups  xmmword ptr [rax], xmm0
0x180038f31  mov     rdx, rdi
0x180038f34  mov     rcx, rbx
0x180038f37  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_6+10h; "urrentControlSet\\Services\\LanmanServe"...
0x180038f3e  movups  xmmword ptr [rax+10h], xmm1
0x180038f42  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6+20h; "ntrolSet\\Services\\LanmanServer\\Certs"...
0x180038f49  movups  xmmword ptr [rax+20h], xmm0
0x180038f4d  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_6+30h; "\\Services\\LanmanServer\\CertsAcl\\"
0x180038f54  movups  xmmword ptr [rax+30h], xmm1
0x180038f58  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6+40h; "s\\LanmanServer\\CertsAcl\\"
0x180038f5f  movups  xmmword ptr [rax+40h], xmm0
0x180038f63  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_6+50h; "Server\\CertsAcl\\"
0x180038f6a  movups  xmmword ptr [rax+50h], xmm1
0x180038f6e  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6+60h; "ertsAcl\\"
0x180038f75  movups  xmmword ptr [rax+60h], xmm0
0x180038f79  movzx   eax, word ptr cs:aSystemCurrentc_6+70h; ""
0x180038f80  mov     [rbx+70h], ax
0x180038f84  call    cs:__imp__o_wcscat_s
0x180038f8a  test    eax, eax
0x180038f8c  jz      short loc_180038FCA
0x180038f8e  mov     edi, 7Ah ; 'z'
0x180038f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f9a  lea     rax, WPP_GLOBAL_Control
0x180038fa1  cmp     rcx, rax
0x180038fa4  jz      short loc_180038FD2
0x180038fa6  test    dword ptr [rcx+1Ch], 800h
0x180038fad  jz      short loc_180038FD2
0x180038faf  cmp     byte ptr [rcx+19h], 1
0x180038fb3  jb      short loc_180038FD2
0x180038fb5  mov     rcx, [rcx+10h]
0x180038fb9  lea     edx, [rdi-1Eh]
0x180038fbc  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180038fc3  call    WPP_SF_
0x180038fc8  jmp     short loc_180038FD2
0x180038fca  mov     [r14], rbx
0x180038fcd  mov     edi, ebp
0x180038fcf  mov     rbx, rbp
0x180038fd2  mov     rcx, rbx
0x180038fd5  call    ClCertLocalFree
0x180038fda  mov     eax, edi
0x180038fdc  add     rsp, 30h
0x180038fe0  pop     r14
0x180038fe2  pop     rdi
0x180038fe3  pop     rsi
0x180038fe4  pop     rbp
0x180038fe5  pop     rbx
0x180038fe6  retn
```
