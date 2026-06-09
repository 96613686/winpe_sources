# ATL::CRegParser::CParseBuffer::Append(ushort const *,int)

- ea: `0x18002f9dc`
- end: `0x18002fa99`
- name: `?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z`
- size: `189`
- prototype: `int(ATL::CRegParser::CParseBuffer *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030434`

## callees

- `0x180006ef0`
- `0x18002f9dc`
- `0x18002fb10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002fa2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002fa2f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CParseBuffer::Append(
        ATL::CRegParser::CParseBuffer *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // ecx
  int v7; // ebx
  unsigned __int64 v8; // rax
  LPVOID v9; // rax
  int v10; // ecx
  errno_t v11; // eax

  v6 = *(_DWORD *)this + a3 + 1;
  if ( v6 > *(_DWORD *)this && v6 > a3 )
  {
    v7 = *((_DWORD *)this + 1);
    if ( v6 < v7 )
    {
LABEL_9:
      if ( *(int *)this >= 0 && *(_DWORD *)this < v7 )
      {
        v10 = v7 - *(_DWORD *)this;
        if ( v10 <= v7 )
        {
          v11 = memcpy_s((void *const)(*((_QWORD *)this + 1) + 2LL * *(int *)this), 2LL * v10, a2, 2 * a3);
          ATL::AtlCrtErrorCheck(v11);
          *(_DWORD *)this += a3;
          *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(int *)this) = 0;
          return 1;
        }
      }
    }
    else
    {
      while ( v7 <= 0x3FFFFFFF )
      {
        v7 *= 2;
        if ( v6 < v7 )
        {
          v8 = 2LL * (unsigned int)v7;
          if ( v8 <= 0xFFFFFFFF )
          {
            v9 = CoTaskMemRealloc(*((LPVOID *)this + 1), (unsigned int)v8);
            if ( v9 )
            {
              *((_QWORD *)this + 1) = v9;
              *((_DWORD *)this + 1) = v7;
              goto LABEL_9;
            }
          }
          return 0;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002f9dc  push    rbx
0x18002f9de  push    rbp
0x18002f9df  push    rsi
0x18002f9e0  push    rdi
0x18002f9e1  sub     rsp, 28h
0x18002f9e5  mov     rdi, rcx
0x18002f9e8  mov     esi, r8d
0x18002f9eb  lea     ecx, [r8+1]
0x18002f9ef  mov     rbp, rdx
0x18002f9f2  add     ecx, [rdi]
0x18002f9f4  cmp     ecx, [rdi]
0x18002f9f6  jle     loc_18002FA8E
0x18002f9fc  cmp     ecx, r8d
0x18002f9ff  jle     loc_18002FA8E
0x18002fa05  mov     ebx, [rdi+4]
0x18002fa08  cmp     ecx, ebx
0x18002fa0a  jl      short loc_18002FA41
0x18002fa0c  cmp     ebx, 3FFFFFFFh
0x18002fa12  jg      short loc_18002FA8E
0x18002fa14  add     ebx, ebx
0x18002fa16  cmp     ecx, ebx
0x18002fa18  jge     short loc_18002FA0C
0x18002fa1a  mov     eax, ebx
0x18002fa1c  mov     ecx, 0FFFFFFFFh
0x18002fa21  add     rax, rax
0x18002fa24  cmp     rax, rcx
0x18002fa27  ja      short loc_18002FA8E
0x18002fa29  mov     rcx, [rdi+8]; pv
0x18002fa2d  mov     edx, eax; cb
0x18002fa2f  call    cs:__imp_CoTaskMemRealloc
0x18002fa35  test    rax, rax
0x18002fa38  jz      short loc_18002FA8E
0x18002fa3a  mov     [rdi+8], rax
0x18002fa3e  mov     [rdi+4], ebx
0x18002fa41  cmp     dword ptr [rdi], 0
0x18002fa44  jl      short loc_18002FA8E
0x18002fa46  cmp     [rdi], ebx
0x18002fa48  jge     short loc_18002FA8E
0x18002fa4a  mov     ecx, ebx
0x18002fa4c  sub     ecx, [rdi]
0x18002fa4e  cmp     ecx, ebx
0x18002fa50  jg      short loc_18002FA8E
0x18002fa52  movsxd  rdx, ecx
0x18002fa55  lea     eax, [rsi+rsi]
0x18002fa58  movsxd  rcx, dword ptr [rdi]
0x18002fa5b  add     rdx, rdx; DestinationSize
0x18002fa5e  movsxd  r9, eax; SourceSize
0x18002fa61  mov     r8, rbp; Source
0x18002fa64  mov     rax, [rdi+8]
0x18002fa68  lea     rcx, [rax+rcx*2]; Destination
0x18002fa6c  call    memcpy_s
0x18002fa71  mov     ecx, eax; int
0x18002fa73  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002fa78  add     [rdi], esi
0x18002fa7a  movsxd  rdx, dword ptr [rdi]
0x18002fa7d  xor     eax, eax
0x18002fa7f  mov     rcx, [rdi+8]
0x18002fa83  mov     [rcx+rdx*2], ax
0x18002fa87  mov     eax, 1
0x18002fa8c  jmp     short loc_18002FA90
0x18002fa8e  xor     eax, eax
0x18002fa90  add     rsp, 28h
0x18002fa94  pop     rdi
0x18002fa95  pop     rsi
0x18002fa96  pop     rbp
0x18002fa97  pop     rbx
0x18002fa98  retn
```
