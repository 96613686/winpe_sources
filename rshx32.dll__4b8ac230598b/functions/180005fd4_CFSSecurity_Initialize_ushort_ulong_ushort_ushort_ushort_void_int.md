# CFSSecurity::Initialize(ushort *,ulong,ushort *,ushort *,ushort *,void *,int)

- ea: `0x180005fd4`
- end: `0x180006104`
- name: `?Initialize@CFSSecurity@@QEAAJPEAGK000PEAXH@Z`
- size: `304`
- prototype: `__int64 __fastcall(CFSSecurity *this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, PSECURITY_DESCRIPTOR pSecurityDescriptor, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005b00`

## callees

- `0x180005fd4`
- `0x180007390`
- `0x18000ae80`
- `0x18001654c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800060f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006093`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006093`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180006024`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180006024`

## pseudocode

```c
__int64 __fastcall CFSSecurity::Initialize(
        CFSSecurity *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        int a8)
{
  unsigned int v10; // edi
  unsigned __int16 *v12; // rsi
  HLOCAL v13; // rcx
  CShareSecurityInformation *v14; // rax
  CShareSecurityInformation *v15; // rbx
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-30h] BYREF

  v10 = CNTFSSecurity::Initialize(this, a2, a3, a4, a5, a8);
  if ( !v10 && pSecurityDescriptor )
  {
    if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
      return 2147942487LL;
    v12 = a6;
    v17 = a6;
    hMem = 0;
    v10 = LocalAllocString((unsigned __int16 **)&hMem, a4);
    if ( !v10 )
    {
      if ( !a6 )
      {
        v10 = LocalAllocString(&v17, a5);
        if ( v10 )
        {
          v13 = hMem;
LABEL_15:
          LocalFree(v13);
          return v10;
        }
        v12 = v17;
      }
      v14 = (CShareSecurityInformation *)LocalAlloc(0x40u, 0x110u);
      v15 = v14;
      if ( v14 )
      {
        CShareSecurityInformation::CShareSecurityInformation(v14, v12, (unsigned __int16 *)hMem, pSecurityDescriptor);
        *((_DWORD *)v15 + 66) = 2576;
        *(_QWORD *)v15 = &CFSShareSecurityInformation::`vftable';
      }
      else
      {
        v15 = 0;
      }
      *((_QWORD *)this + 79) = v15;
      if ( v15 )
        return v10;
      v10 = -2147467259;
      LocalFree(hMem);
      v13 = v12;
      goto LABEL_15;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180005fd4  push    rbx
0x180005fd6  push    rsi
0x180005fd7  push    rdi
0x180005fd8  push    r14
0x180005fda  push    r15
0x180005fdc  sub     rsp, 40h
0x180005fe0  mov     eax, [rsp+68h+arg_38]
0x180005fe7  mov     r14, r9
0x180005fea  mov     rbx, [rsp+68h+arg_20]
0x180005ff2  mov     r15, rcx
0x180005ff5  mov     [rsp+68h+var_40], eax; int
0x180005ff9  mov     [rsp+68h+var_48], rbx; unsigned __int16 *
0x180005ffe  call    ?Initialize@CNTFSSecurity@@UEAAJPEAGK00H@Z; CNTFSSecurity::Initialize(ushort *,ulong,ushort *,ushort *,int)
0x180006003  mov     edi, eax
0x180006005  test    eax, eax
0x180006007  jnz     loc_1800060F6
0x18000600d  cmp     [rsp+68h+pSecurityDescriptor], 0
0x180006016  jz      loc_1800060F6
0x18000601c  mov     rcx, [rsp+68h+pSecurityDescriptor]; pSecurityDescriptor
0x180006024  call    cs:__imp_IsValidSecurityDescriptor
0x18000602a  test    eax, eax
0x18000602c  jnz     short loc_180006038
0x18000602e  mov     eax, 80070057h
0x180006033  jmp     loc_1800060F8
0x180006038  mov     rsi, [rsp+68h+arg_28]
0x180006040  lea     rcx, [rsp+68h+hMem]; unsigned __int16 **
0x180006045  mov     rdx, r14; unsigned __int16 *
0x180006048  mov     [rsp+68h+var_30], rsi
0x18000604d  mov     [rsp+68h+hMem], 0
0x180006056  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x18000605b  mov     edi, eax
0x18000605d  test    eax, eax
0x18000605f  jnz     loc_1800060F6
0x180006065  test    rsi, rsi
0x180006068  jnz     short loc_180006089
0x18000606a  mov     rdx, rbx; unsigned __int16 *
0x18000606d  lea     rcx, [rsp+68h+var_30]; unsigned __int16 **
0x180006072  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x180006077  mov     edi, eax
0x180006079  test    eax, eax
0x18000607b  jz      short loc_180006084
0x18000607d  mov     rcx, [rsp+68h+hMem]
0x180006082  jmp     short loc_1800060F0
0x180006084  mov     rsi, [rsp+68h+var_30]
0x180006089  mov     edx, 110h; uBytes
0x18000608e  mov     ecx, 40h ; '@'; uFlags
0x180006093  call    cs:__imp_LocalAlloc
0x180006099  mov     rbx, rax
0x18000609c  test    rax, rax
0x18000609f  jz      short loc_1800060CF
0x1800060a1  mov     r9, [rsp+68h+pSecurityDescriptor]; void *
0x1800060a9  mov     rdx, rsi; unsigned __int16 *
0x1800060ac  mov     r8, [rsp+68h+hMem]; unsigned __int16 *
0x1800060b1  mov     rcx, rax; this
0x1800060b4  call    ??0CShareSecurityInformation@@QEAA@PEAG0PEAX@Z; CShareSecurityInformation::CShareSecurityInformation(ushort *,ushort *,void *)
0x1800060b9  lea     rax, ??_7CFSShareSecurityInformation@@6B@; const CFSShareSecurityInformation::`vftable'
0x1800060c0  mov     dword ptr [rbx+108h], 0A10h
0x1800060ca  mov     [rbx], rax
0x1800060cd  jmp     short loc_1800060D1
0x1800060cf  xor     ebx, ebx
0x1800060d1  mov     [r15+278h], rbx
0x1800060d8  test    rbx, rbx
0x1800060db  jnz     short loc_1800060F6
0x1800060dd  mov     rcx, [rsp+68h+hMem]; hMem
0x1800060e2  mov     edi, 80004005h
0x1800060e7  call    cs:__imp_LocalFree
0x1800060ed  mov     rcx, rsi; hMem
0x1800060f0  call    cs:__imp_LocalFree
0x1800060f6  mov     eax, edi
0x1800060f8  add     rsp, 40h
0x1800060fc  pop     r15
0x1800060fe  pop     r14
0x180006100  pop     rdi
0x180006101  pop     rsi
0x180006102  pop     rbx
0x180006103  retn
```
