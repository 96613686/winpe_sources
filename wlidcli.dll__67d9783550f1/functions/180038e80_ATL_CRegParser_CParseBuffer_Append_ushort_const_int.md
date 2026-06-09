# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x180038e80`
- end: `0x180038f54`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegParser::CParseBuffer *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039c54`

## callees

- `0x18000a1a8`
- `0x18000ac9c`
- `0x180038418`
- `0x180038e80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180038eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180038eea`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  LPVOID v8; // rax
  int v9; // ecx
  errno_t v10; // eax
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 >= v7 )
    {
      while ( v6 >= v7 )
      {
        if ( v7 > 0x3FFFFFFF )
          return 0;
        v7 *= 2;
      }
      LODWORD(cb) = 0;
      if ( (int)ATL::AtlMultiply<unsigned long>(&cb, (unsigned int)v7, 2) < 0 )
        return 0;
      v8 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)cb);
      if ( !v8 )
        return 0;
      *((_QWORD *)this + 1) = v8;
      *((_DWORD *)this + 1) = v7;
    }
    if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
    {
      v9 = v7 - *(_DWORD *)this;
      if ( v9 <= v7 )
      {
        v10 = memcpy_s_0((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v9, a2, 2 * a3);
        ATL::AtlCrtErrorCheck(v10);
        *(_DWORD *)this += a3;
        *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180038e80  push    rbx
0x180038e82  push    rbp
0x180038e83  push    rsi
0x180038e84  push    rdi
0x180038e85  sub     rsp, 28h
0x180038e89  mov     rdi, rcx
0x180038e8c  mov     esi, r8d
0x180038e8f  lea     ecx, [r8+1]
0x180038e93  mov     rbp, rdx
0x180038e96  add     ecx, [rdi]
0x180038e98  cmp     ecx, [rdi]
0x180038e9a  jle     loc_180038F49
0x180038ea0  cmp     ecx, r8d
0x180038ea3  jle     loc_180038F49
0x180038ea9  mov     ebx, [rdi+4]
0x180038eac  cmp     ecx, ebx
0x180038eae  jl      short loc_180038EFC
0x180038eb0  cmp     ecx, ebx
0x180038eb2  jl      short loc_180038EC4
0x180038eb4  cmp     ebx, 3FFFFFFFh
0x180038eba  jg      loc_180038F49
0x180038ec0  add     ebx, ebx
0x180038ec2  jmp     short loc_180038EB0
0x180038ec4  mov     r8d, 2
0x180038eca  mov     dword ptr [rsp+48h+cb], 0
0x180038ed2  mov     edx, ebx
0x180038ed4  lea     rcx, [rsp+48h+cb]
0x180038ed9  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180038ede  test    eax, eax
0x180038ee0  js      short loc_180038F49
0x180038ee2  mov     edx, dword ptr [rsp+48h+cb]; cb
0x180038ee6  mov     rcx, [rdi+8]; pv
0x180038eea  call    cs:__imp_CoTaskMemRealloc
0x180038ef0  test    rax, rax
0x180038ef3  jz      short loc_180038F49
0x180038ef5  mov     [rdi+8], rax
0x180038ef9  mov     [rdi+4], ebx
0x180038efc  cmp     dword ptr [rdi], 0
0x180038eff  jl      short loc_180038F49
0x180038f01  cmp     [rdi], ebx
0x180038f03  jge     short loc_180038F49
0x180038f05  mov     ecx, ebx
0x180038f07  sub     ecx, [rdi]
0x180038f09  cmp     ecx, ebx
0x180038f0b  jg      short loc_180038F49
0x180038f0d  movsxd  rdx, ecx
0x180038f10  lea     eax, [rsi+rsi]
0x180038f13  movsxd  rcx, dword ptr [rdi]
0x180038f16  add     rdx, rdx; DestinationSize
0x180038f19  movsxd  r9, eax; SourceSize
0x180038f1c  mov     r8, rbp; Source
0x180038f1f  mov     rax, [rdi+8]
0x180038f23  lea     rcx, [rax+rcx*2]; Destination
0x180038f27  call    memcpy_s_0
0x180038f2c  mov     ecx, eax; int
0x180038f2e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180038f33  add     [rdi], esi
0x180038f35  movsxd  rdx, dword ptr [rdi]
0x180038f38  xor     eax, eax
0x180038f3a  mov     rcx, [rdi+8]
0x180038f3e  mov     [rcx+rdx*2], ax
0x180038f42  mov     eax, 1
0x180038f47  jmp     short loc_180038F4B
0x180038f49  xor     eax, eax
0x180038f4b  add     rsp, 28h
0x180038f4f  pop     rdi
0x180038f50  pop     rsi
0x180038f51  pop     rbp
0x180038f52  pop     rbx
0x180038f53  retn
```
