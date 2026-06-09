# CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(CSxVolumeInfo *)

- ea: `0x18000406c`
- end: `0x18000411e`
- name: `?Append@?$CSxRefArray@VCSxVolumeInfoArray@@VCSxVolumeInfo@@@@QEAAJPEAVCSxVolumeInfo@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a830`
- `0x18001ac40`
- `0x180023874`
- `0x180023fc4`
- `0x180024b8c`
- `0x180028ee8`

## callees

- `0x18000406c`
- `0x18000f8ac`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800040cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800040cd`

## pseudocode

```c
__int64 __fastcall CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(__int64 a1, volatile signed __int32 *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ebp
  unsigned int v7; // r14d
  LPVOID v8; // rax
  SIZE_T cb; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    v5 = *(_DWORD *)(a1 + 8);
    v6 = v5 + 1;
    if ( v5 + 1 < v5 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v4 = 0;
      cb = 0;
      if ( v6 > *(_DWORD *)(a1 + 12) )
      {
        v7 = SxScaledGrowth(v6);
        v4 = ULongLongMult(v7, 8u, &cb);
        if ( v4 >= 0 )
        {
          v8 = CoTaskMemRealloc(*(LPVOID *)a1, cb);
          if ( v8 )
          {
            *(_QWORD *)a1 = v8;
            *(_DWORD *)(a1 + 12) = v7;
          }
          else
          {
            v4 = -2147024882;
          }
        }
      }
      CoTaskMemFree(0);
      if ( v4 >= 0 )
      {
        _InterlockedIncrement(a2);
        *(_QWORD *)(*(_QWORD *)a1 + 8LL * *(unsigned int *)(a1 + 8)) = a2;
        *(_DWORD *)(a1 + 8) = v6;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000406c  mov     [rsp+arg_0], rbx
0x180004071  mov     [rsp+arg_10], rbp
0x180004076  push    rsi
0x180004077  push    rdi
0x180004078  push    r14
0x18000407a  sub     rsp, 20h
0x18000407e  mov     rsi, rdx
0x180004081  mov     rdi, rcx
0x180004084  test    rdx, rdx
0x180004087  jnz     short loc_180004090
0x180004089  mov     ebx, 80070057h
0x18000408e  jmp     short loc_180004109
0x180004090  mov     eax, [rcx+8]
0x180004093  lea     ebp, [rax+1]
0x180004096  cmp     ebp, eax
0x180004098  jb      short loc_180004104
0x18000409a  xor     ebx, ebx
0x18000409c  mov     [rsp+38h+cb], rbx
0x1800040a1  cmp     ebp, [rcx+0Ch]
0x1800040a4  jbe     short loc_1800040E6
0x1800040a6  mov     ecx, ebp; unsigned int
0x1800040a8  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1800040ad  mov     ecx, eax; unsigned __int64
0x1800040af  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x1800040b4  lea     edx, [rbx+8]; unsigned __int64
0x1800040b7  mov     r14d, eax
0x1800040ba  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800040bf  mov     ebx, eax
0x1800040c1  test    eax, eax
0x1800040c3  js      short loc_1800040E6
0x1800040c5  mov     rdx, [rsp+38h+cb]; cb
0x1800040ca  mov     rcx, [rdi]; pv
0x1800040cd  call    cs:__imp_CoTaskMemRealloc
0x1800040d3  test    rax, rax
0x1800040d6  jnz     short loc_1800040DF
0x1800040d8  mov     ebx, 8007000Eh
0x1800040dd  jmp     short loc_1800040E6
0x1800040df  mov     [rdi], rax
0x1800040e2  mov     [rdi+0Ch], r14d
0x1800040e6  xor     ecx, ecx; pv
0x1800040e8  call    cs:__imp_CoTaskMemFree
0x1800040ee  test    ebx, ebx
0x1800040f0  js      short loc_180004109
0x1800040f2  lock inc dword ptr [rsi]
0x1800040f5  mov     ecx, [rdi+8]
0x1800040f8  mov     rax, [rdi]
0x1800040fb  mov     [rax+rcx*8], rsi
0x1800040ff  mov     [rdi+8], ebp
0x180004102  jmp     short loc_180004109
0x180004104  mov     ebx, 80070216h
0x180004109  mov     rbp, [rsp+38h+arg_10]
0x18000410e  mov     eax, ebx
0x180004110  mov     rbx, [rsp+38h+arg_0]
0x180004115  add     rsp, 20h
0x180004119  pop     r14
0x18000411b  pop     rdi
0x18000411c  pop     rsi
0x18000411d  retn
```
