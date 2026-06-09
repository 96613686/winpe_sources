# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18001d92c`
- end: `0x18001da00`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `212`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e660`

## callees

- `0x180011af8`
- `0x180015788`
- `0x1800163d8`
- `0x18001d92c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001d996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001d996`

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
        v10 = memcpy_s_1((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v9, a2, 2 * a3);
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
0x18001d92c  push    rbx
0x18001d92e  push    rbp
0x18001d92f  push    rsi
0x18001d930  push    rdi
0x18001d931  sub     rsp, 28h
0x18001d935  mov     rdi, rcx
0x18001d938  mov     esi, r8d
0x18001d93b  lea     ecx, [r8+1]
0x18001d93f  mov     rbp, rdx
0x18001d942  add     ecx, [rdi]
0x18001d944  cmp     ecx, [rdi]
0x18001d946  jle     loc_18001D9F5
0x18001d94c  cmp     ecx, r8d
0x18001d94f  jle     loc_18001D9F5
0x18001d955  mov     ebx, [rdi+4]
0x18001d958  cmp     ecx, ebx
0x18001d95a  jl      short loc_18001D9A8
0x18001d95c  cmp     ecx, ebx
0x18001d95e  jl      short loc_18001D970
0x18001d960  cmp     ebx, 3FFFFFFFh
0x18001d966  jg      loc_18001D9F5
0x18001d96c  add     ebx, ebx
0x18001d96e  jmp     short loc_18001D95C
0x18001d970  mov     r8d, 2
0x18001d976  mov     dword ptr [rsp+48h+cb], 0
0x18001d97e  mov     edx, ebx
0x18001d980  lea     rcx, [rsp+48h+cb]
0x18001d985  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18001d98a  test    eax, eax
0x18001d98c  js      short loc_18001D9F5
0x18001d98e  mov     edx, dword ptr [rsp+48h+cb]; cb
0x18001d992  mov     rcx, [rdi+8]; pv
0x18001d996  call    cs:__imp_CoTaskMemRealloc
0x18001d99c  test    rax, rax
0x18001d99f  jz      short loc_18001D9F5
0x18001d9a1  mov     [rdi+8], rax
0x18001d9a5  mov     [rdi+4], ebx
0x18001d9a8  cmp     dword ptr [rdi], 0
0x18001d9ab  jl      short loc_18001D9F5
0x18001d9ad  cmp     [rdi], ebx
0x18001d9af  jge     short loc_18001D9F5
0x18001d9b1  mov     ecx, ebx
0x18001d9b3  sub     ecx, [rdi]
0x18001d9b5  cmp     ecx, ebx
0x18001d9b7  jg      short loc_18001D9F5
0x18001d9b9  movsxd  rdx, ecx
0x18001d9bc  lea     eax, [rsi+rsi]
0x18001d9bf  movsxd  rcx, dword ptr [rdi]
0x18001d9c2  add     rdx, rdx; DestinationSize
0x18001d9c5  movsxd  r9, eax; SourceSize
0x18001d9c8  mov     r8, rbp; Source
0x18001d9cb  mov     rax, [rdi+8]
0x18001d9cf  lea     rcx, [rax+rcx*2]; Destination
0x18001d9d3  call    memcpy_s_1
0x18001d9d8  mov     ecx, eax; int
0x18001d9da  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001d9df  add     [rdi], esi
0x18001d9e1  movsxd  rdx, dword ptr [rdi]
0x18001d9e4  xor     eax, eax
0x18001d9e6  mov     rcx, [rdi+8]
0x18001d9ea  mov     [rcx+rdx*2], ax
0x18001d9ee  mov     eax, 1
0x18001d9f3  jmp     short loc_18001D9F7
0x18001d9f5  xor     eax, eax
0x18001d9f7  add     rsp, 28h
0x18001d9fb  pop     rdi
0x18001d9fc  pop     rsi
0x18001d9fd  pop     rbp
0x18001d9fe  pop     rbx
0x18001d9ff  retn
```
