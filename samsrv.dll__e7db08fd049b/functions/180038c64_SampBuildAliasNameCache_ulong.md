# SampBuildAliasNameCache(ulong)

- ea: `0x180038c64`
- end: `0x180038eb7`
- name: `?SampBuildAliasNameCache@@YAJK@Z`
- size: `595`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180038ec0`

## callees

- `0x180003a40`
- `0x180027c30`
- `0x180027e24`
- `0x18002d720`
- `0x180038c64`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180038db6`
- `ntdll!RtlCopyUnicodeString` at `0x180038db6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038cff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038d31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038d7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038cff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038d31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038d7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e6b`
- `LSASRV!LsaIRegisterNotification` at `0x180038e15`
- `LSASRV!LsaIRegisterNotification` at `0x180038e15`

## pseudocode

```c
__int64 __fastcall SampBuildAliasNameCache(unsigned int a1)
{
  __int64 v1; // r14
  __int64 v2; // rcx
  __int64 v3; // rbx
  int v4; // edi
  __int64 v5; // r13
  _OWORD *v6; // rax
  unsigned int v7; // esi
  HLOCAL v8; // rax
  unsigned int i; // esi
  __int64 v10; // rbp
  __int64 v11; // r12
  __int64 v12; // r15
  HLOCAL v13; // rax
  __int16 v14; // ax
  __int64 v15; // rdx
  unsigned int j; // esi
  void *v17; // rcx
  unsigned int v19; // [rsp+90h] [rbp+8h] BYREF
  int v20; // [rsp+98h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp+18h] BYREF

  v1 = 1360LL * a1;
  v2 = *(_QWORD *)((char *)SampDefinedDomains + v1);
  v3 = 0;
  v20 = 0;
  hMem = 0;
  v19 = 0;
  v4 = SampEnumerateAccountNames2(v2, 3, &v20, 0, &hMem, -1, 0, &v19, 1);
  if ( v4 >= 0 )
  {
    if ( !hMem )
    {
      v4 = -1073741670;
      goto LABEL_24;
    }
    v5 = *((_QWORD *)hMem + 1);
    v6 = LocalAlloc(0x40u, 0x10u);
    v3 = (__int64)v6;
    if ( v6 && (*v6 = 0, v7 = 24 * v19, v8 = LocalAlloc(0x40u, 24 * v19), (*(_QWORD *)(v3 + 8) = v8) != 0) )
    {
      memset_0(v8, 0, v7);
      for ( i = 0; i < v19; ++i )
      {
        v10 = 3LL * i;
        v11 = v5 + 24LL * i;
        v12 = *(_QWORD *)(v3 + 8) + 24LL * i;
        v13 = LocalAlloc(0x40u, *(unsigned __int16 *)(v11 + 8));
        *(_QWORD *)(v12 + 16) = v13;
        if ( !v13 )
        {
          v4 = -1073741801;
          goto LABEL_14;
        }
        memset_0(v13, 0, *(unsigned __int16 *)(v11 + 8));
        v14 = *(_WORD *)(v11 + 8);
        *(_WORD *)(v12 + 10) = v14;
        *(_WORD *)(v12 + 8) = v14;
        RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 8), (PCUNICODE_STRING)(v11 + 8));
        *(_DWORD *)(*(_QWORD *)(v3 + 8) + 8 * v10) = *(_DWORD *)(v5 + 8 * v10);
      }
      *(_DWORD *)v3 = v19;
      v15 = _InterlockedExchange64((volatile __int64 *)((char *)SampDefinedDomains + v1 + 1344), v3);
      v3 = 0;
      if ( v15 )
        LsaIRegisterNotification(SampFreeAliasNameCache, v15, 1, 0, 2, 3600, 0);
    }
    else
    {
      v4 = -1073741801;
    }
  }
LABEL_14:
  if ( hMem )
    SamIFree_SAMPR_ENUMERATION_BUFFER(hMem);
  if ( v3 )
  {
    if ( *(_QWORD *)(v3 + 8) )
    {
      for ( j = 0; j < *(_DWORD *)v3; ++j )
      {
        v17 = *(void **)(*(_QWORD *)(v3 + 8) + 24LL * j + 16);
        if ( v17 )
          LocalFree(v17);
      }
      LocalFree(*(HLOCAL *)(v3 + 8));
    }
    LocalFree((HLOCAL)v3);
  }
LABEL_24:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 50, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, (unsigned int)v4, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180038c64  mov     r11, rsp
0x180038c67  mov     [r11+20h], rbx
0x180038c6b  push    rbp
0x180038c6c  push    rsi
0x180038c6d  push    rdi
0x180038c6e  push    r12
0x180038c70  push    r13
0x180038c72  push    r14
0x180038c74  push    r15
0x180038c76  sub     rsp, 50h
0x180038c7a  xor     ebp, ebp
0x180038c7c  mov     eax, ecx
0x180038c7e  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180038c85  lea     r8, [r11+10h]
0x180038c89  imul    r14, rax, 550h
0x180038c90  mov     [rsp+88h+var_48], 1
0x180038c95  lea     rax, [r11+8]
0x180038c99  mov     [r11-50h], rax
0x180038c9d  lea     edx, [rbp+3]
0x180038ca0  mov     dword ptr [rsp+88h+var_58], ebp
0x180038ca4  lea     rax, [r11+18h]
0x180038ca8  mov     [rsp+88h+var_60], 0FFFFFFFFh
0x180038cb0  xor     r9d, r9d
0x180038cb3  mov     rcx, [r14+rcx]
0x180038cb7  mov     ebx, ebp
0x180038cb9  mov     [r11+10h], ebp
0x180038cbd  mov     [r11+18h], rbp
0x180038cc1  mov     [r11+8], ebp
0x180038cc5  mov     [r11-68h], rax
0x180038cc9  call    ?SampEnumerateAccountNames2@@YAJPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@PEAKKPEAPEAU_SAMPR_ENUMERATION_BUFFER@@KK2E@Z; SampEnumerateAccountNames2(_SAMP_OBJECT *,_SAMP_OBJECT_TYPE,ulong *,ulong,_SAMPR_ENUMERATION_BUFFER * *,ulong,ulong,ulong *,uchar)
0x180038cce  mov     edi, eax
0x180038cd0  test    eax, eax
0x180038cd2  js      loc_180038E1B
0x180038cd8  mov     rax, [rsp+88h+hMem]
0x180038ce0  test    rax, rax
0x180038ce3  jnz     short loc_180038CEF
0x180038ce5  mov     edi, 0C000009Ah
0x180038cea  jmp     loc_180038E71
0x180038cef  mov     r13, [rax+8]
0x180038cf3  mov     edx, 10h; uBytes
0x180038cf8  lea     r15d, [rdx+30h]
0x180038cfc  mov     ecx, r15d; uFlags
0x180038cff  call    cs:__imp_LocalAlloc
0x180038d05  mov     rbx, rax
0x180038d08  test    rax, rax
0x180038d0b  jnz     short loc_180038D17
0x180038d0d  mov     edi, 0C0000017h
0x180038d12  jmp     loc_180038E1B
0x180038d17  xorps   xmm0, xmm0
0x180038d1a  movups  xmmword ptr [rax], xmm0
0x180038d1d  mov     eax, [rsp+88h+arg_0]
0x180038d24  lea     ecx, [rax+rax*2]
0x180038d27  shl     ecx, 3
0x180038d2a  mov     esi, ecx
0x180038d2c  mov     edx, ecx; uBytes
0x180038d2e  mov     ecx, r15d; uFlags
0x180038d31  call    cs:__imp_LocalAlloc
0x180038d37  mov     [rbx+8], rax
0x180038d3b  test    rax, rax
0x180038d3e  jz      short loc_180038D0D
0x180038d40  mov     r8d, esi; Size
0x180038d43  xor     edx, edx; Val
0x180038d45  mov     rcx, rax; void *
0x180038d48  call    memset_0
0x180038d4d  mov     esi, ebp
0x180038d4f  mov     eax, [rsp+88h+arg_0]
0x180038d56  cmp     esi, eax
0x180038d58  jnb     short loc_180038DD5
0x180038d5a  mov     eax, esi
0x180038d5c  mov     ecx, 40h ; '@'; uFlags
0x180038d61  lea     rbp, [rax+rax*2]
0x180038d65  mov     rax, [rbx+8]
0x180038d69  lea     r12, ds:0[rbp*8]
0x180038d71  add     r12, r13
0x180038d74  lea     r15, [rax+rbp*8]
0x180038d78  movzx   edx, word ptr [r12+8]; uBytes
0x180038d7e  call    cs:__imp_LocalAlloc
0x180038d84  mov     [r15+10h], rax
0x180038d88  test    rax, rax
0x180038d8b  jz      short loc_180038DCC
0x180038d8d  movzx   r8d, word ptr [r12+8]; Size
0x180038d93  xor     edx, edx; Val
0x180038d95  mov     rcx, rax; void *
0x180038d98  call    memset_0
0x180038d9d  movzx   eax, word ptr [r12+8]
0x180038da3  lea     rdx, [r12+8]; SourceString
0x180038da8  lea     rcx, [r15+8]; DestinationString
0x180038dac  mov     [r15+0Ah], ax
0x180038db1  mov     [r15+8], ax
0x180038db6  call    cs:__imp_RtlCopyUnicodeString
0x180038dbc  mov     rcx, [rbx+8]
0x180038dc0  inc     esi
0x180038dc2  mov     eax, [r13+rbp*8+0]
0x180038dc7  mov     [rcx+rbp*8], eax
0x180038dca  jmp     short loc_180038D4F
0x180038dcc  mov     edi, 0C0000017h
0x180038dd1  xor     ebp, ebp
0x180038dd3  jmp     short loc_180038E1B
0x180038dd5  mov     [rbx], eax
0x180038dd7  xor     ebp, ebp
0x180038dd9  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180038de0  xchg    rbx, [r14+rax+540h]
0x180038de8  mov     rdx, rbx
0x180038deb  mov     ebx, ebp
0x180038ded  test    rdx, rdx
0x180038df0  jz      short loc_180038E1B
0x180038df2  mov     [rsp+88h+var_58], rbp
0x180038df7  lea     r8d, [rbp+1]
0x180038dfb  mov     [rsp+88h+var_60], 0E10h
0x180038e03  lea     rcx, ?SampFreeAliasNameCache@@YAJPEAX@Z; SampFreeAliasNameCache(void *)
0x180038e0a  xor     r9d, r9d
0x180038e0d  mov     [rsp+88h+var_68], 2
0x180038e15  call    cs:__imp_LsaIRegisterNotification
0x180038e1b  mov     rcx, [rsp+88h+hMem]; hMem
0x180038e23  test    rcx, rcx
0x180038e26  jz      short loc_180038E2D
0x180038e28  call    SamIFree_SAMPR_ENUMERATION_BUFFER
0x180038e2d  test    rbx, rbx
0x180038e30  jz      short loc_180038E71
0x180038e32  cmp     [rbx+8], rbp
0x180038e36  jz      short loc_180038E68
0x180038e38  mov     esi, ebp
0x180038e3a  cmp     [rbx], ebp
0x180038e3c  jbe     short loc_180038E5E
0x180038e3e  mov     eax, esi
0x180038e40  lea     rcx, [rax+rax*2]
0x180038e44  mov     rax, [rbx+8]
0x180038e48  mov     rcx, [rax+rcx*8+10h]; hMem
0x180038e4d  test    rcx, rcx
0x180038e50  jz      short loc_180038E58
0x180038e52  call    cs:__imp_LocalFree
0x180038e58  inc     esi
0x180038e5a  cmp     esi, [rbx]
0x180038e5c  jb      short loc_180038E3E
0x180038e5e  mov     rcx, [rbx+8]; hMem
0x180038e62  call    cs:__imp_LocalFree
0x180038e68  mov     rcx, rbx; hMem
0x180038e6b  call    cs:__imp_LocalFree
0x180038e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e78  test    dword ptr [rcx+44h], 20000h
0x180038e7f  jz      short loc_180038E9D
0x180038e81  mov     rcx, [rcx+38h]
0x180038e85  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x180038e8c  mov     edx, 32h ; '2'
0x180038e91  mov     [rsp+88h+var_68], edi
0x180038e95  mov     r9d, edi
0x180038e98  call    WPP_SF_Dd
0x180038e9d  mov     rbx, [rsp+88h+arg_18]
0x180038ea5  mov     eax, edi
0x180038ea7  add     rsp, 50h
0x180038eab  pop     r15
0x180038ead  pop     r14
0x180038eaf  pop     r13
0x180038eb1  pop     r12
0x180038eb3  pop     rdi
0x180038eb4  pop     rsi
0x180038eb5  pop     rbp
0x180038eb6  retn
```
