# RtmDeleteNextHop

- ea: `0x180008ba0`
- end: `0x180008d36`
- name: `RtmDeleteNextHop`
- size: `406`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_NEXTHOP_HANDLE NextHopHandle, PRTM_NEXTHOP_INFO NextHopInfo)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008ebc`

## callees

- `0x180001de0`
- `0x180008868`
- `0x180008ba0`
- `0x18000a230`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180008c18`
- `ntdll!RtlAcquireResourceExclusive` at `0x180008c18`
- `ntdll!RtlReleaseResource` at `0x180008d13`
- `ntdll!RtlReleaseResource` at `0x180008d13`
- `KERNEL32!GetProcessHeap` at `0x180008cc8`
- `KERNEL32!GetProcessHeap` at `0x180008cc8`
- `KERNEL32!HeapFree` at `0x180008cd6`
- `KERNEL32!HeapFree` at `0x180008cd6`

## pseudocode

```c
DWORD __stdcall RtmDeleteNextHop(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_NEXTHOP_HANDLE NextHopHandle,
        PRTM_NEXTHOP_INFO NextHopInfo)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rbx
  DWORD NextHop; // esi
  _BYTE *v9; // r9
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE v15[88]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+90h] [rbp+8h] BYREF

  v16 = 0;
  memset(v15, 0, 32);
  v5 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle != 0x7754DF32
    && *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) != 1 )
  {
    v6 = 0;
    if ( !NextHopHandle )
      goto LABEL_7;
    v6 = (unsigned __int64)NextHopHandle ^ 0x7754DF32;
    if ( (unsigned __int64)NextHopHandle != 0x7754DF32 )
    {
      if ( *(RTM_ENTITY_HANDLE *)(((unsigned __int64)NextHopHandle ^ 0x7754DF32) + 0x30) != RtmRegHandle )
        return 5;
LABEL_7:
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v5 + 224), 1u);
      if ( v6 )
      {
        NextHop = 31;
        if ( *(_WORD *)(v6 + 60) != 1 )
        {
          v9 = 0;
LABEL_12:
          *(_WORD *)(v6 + 60) = 1;
          v10 = *(_QWORD *)(v6 + 8);
          if ( *(_QWORD *)(v10 + 8) != v6 + 8 || (v11 = *(_QWORD **)(v6 + 16), *v11 != v6 + 8) )
            __fastfail(3u);
          v12 = *(_QWORD **)(v6 + 16);
          *v11 = v10;
          *(_QWORD *)(v10 + 8) = v11;
          if ( (_QWORD *)*v12 == v12 )
          {
            v13 = v12 - 2;
            DeleteFromTable(*(_QWORD *)(v5 + 328), *(unsigned __int16 *)(v6 + 26), v6 + 28, v9, &v16);
            if ( v13 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v13);
            }
          }
          --*(_DWORD *)(v5 + 336);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
            DestroyNextHop((LPVOID)v6);
          if ( NextHopHandle )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
              DestroyNextHop((LPVOID)v6);
          }
          NextHop = 0;
        }
      }
      else
      {
        NextHop = FindNextHop(v5, NextHopInfo, v15, &v16);
        if ( !NextHop )
        {
          v9 = v15;
          v6 = v16 - 8;
          goto LABEL_12;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)(v5 + 224));
      return NextHop;
    }
  }
  return 6;
}

```

## disassembly

```asm
0x180008ba0  mov     rax, rsp
0x180008ba3  push    rbx
0x180008ba4  push    rbp
0x180008ba5  push    rsi
0x180008ba6  push    rdi
0x180008ba7  push    r14
0x180008ba9  push    r15
0x180008bab  sub     rsp, 58h
0x180008baf  xorps   xmm0, xmm0
0x180008bb2  mov     qword ptr [rax+8], 0
0x180008bba  movups  xmmword ptr [rax-58h], xmm0
0x180008bbe  mov     rdi, rcx
0x180008bc1  mov     rsi, r8
0x180008bc4  movups  xmmword ptr [rax-48h], xmm0
0x180008bc8  mov     eax, 7754DF32h
0x180008bcd  mov     rbp, rdx
0x180008bd0  xor     rdi, rax
0x180008bd3  jz      loc_180008D24
0x180008bd9  mov     r15d, 1
0x180008bdf  cmp     [rdi+30h], r15d
0x180008be3  jz      loc_180008D24
0x180008be9  xor     ebx, ebx
0x180008beb  test    rdx, rdx
0x180008bee  jz      short loc_180008C0B
0x180008bf0  mov     rbx, rdx
0x180008bf3  xor     rbx, rax
0x180008bf6  jz      loc_180008D24
0x180008bfc  cmp     [rbx+30h], rcx
0x180008c00  jz      short loc_180008C0B
0x180008c02  lea     eax, [r15+4]
0x180008c06  jmp     loc_180008D29
0x180008c0b  lea     r14, [rdi+0E0h]
0x180008c12  mov     dl, r15b; Wait
0x180008c15  mov     rcx, r14; Resource
0x180008c18  call    cs:__imp_RtlAcquireResourceExclusive
0x180008c1e  test    rbx, rbx
0x180008c21  jnz     short loc_180008C58
0x180008c23  lea     r9, [rsp+88h+arg_0]
0x180008c2b  mov     rdx, rsi
0x180008c2e  lea     r8, [rsp+88h+var_58]
0x180008c33  mov     rcx, rdi
0x180008c36  call    FindNextHop
0x180008c3b  mov     esi, eax
0x180008c3d  test    eax, eax
0x180008c3f  jnz     loc_180008D10
0x180008c45  mov     rbx, [rsp+88h+arg_0]
0x180008c4d  lea     r9, [rsp+88h+var_58]
0x180008c52  add     rbx, 0FFFFFFFFFFFFFFF8h
0x180008c56  jmp     short loc_180008C6B
0x180008c58  mov     esi, 1Fh
0x180008c5d  cmp     [rbx+3Ch], r15w
0x180008c62  jz      loc_180008D10
0x180008c68  xor     r9d, r9d
0x180008c6b  lea     rax, [rbx+8]
0x180008c6f  mov     [rbx+3Ch], r15w
0x180008c74  mov     rdx, [rax]
0x180008c77  cmp     [rdx+8], rax
0x180008c7b  jnz     loc_180008D1D
0x180008c81  mov     rcx, [rax+8]
0x180008c85  cmp     [rcx], rax
0x180008c88  jnz     loc_180008D1D
0x180008c8e  mov     rax, [rbx+10h]
0x180008c92  mov     [rcx], rdx
0x180008c95  mov     [rdx+8], rcx
0x180008c99  cmp     [rax], rax
0x180008c9c  jnz     short loc_180008CDC
0x180008c9e  movzx   edx, word ptr [rbx+1Ah]
0x180008ca2  lea     rsi, [rax-10h]
0x180008ca6  mov     rcx, [rdi+148h]
0x180008cad  lea     rax, [rsp+88h+arg_0]
0x180008cb5  lea     r8, [rbx+1Ch]
0x180008cb9  mov     [rsp+88h+var_68], rax
0x180008cbe  call    DeleteFromTable
0x180008cc3  test    rsi, rsi
0x180008cc6  jz      short loc_180008CDC
0x180008cc8  call    cs:__imp_GetProcessHeap
0x180008cce  mov     r8, rsi; lpMem
0x180008cd1  xor     edx, edx; dwFlags
0x180008cd3  mov     rcx, rax; hHeap
0x180008cd6  call    cs:__imp_HeapFree
0x180008cdc  dec     dword ptr [rdi+150h]
0x180008ce2  or      edi, 0FFFFFFFFh
0x180008ce5  mov     eax, edi
0x180008ce7  lock xadd [rbx], eax
0x180008ceb  add     eax, edi
0x180008ced  jnz     short loc_180008CF7
0x180008cef  mov     rcx, rbx; lpMem
0x180008cf2  call    DestroyNextHop
0x180008cf7  test    rbp, rbp
0x180008cfa  jz      short loc_180008D0E
0x180008cfc  mov     eax, edi
0x180008cfe  lock xadd [rbx], eax
0x180008d02  add     eax, edi
0x180008d04  jnz     short loc_180008D0E
0x180008d06  mov     rcx, rbx; lpMem
0x180008d09  call    DestroyNextHop
0x180008d0e  xor     esi, esi
0x180008d10  mov     rcx, r14; Resource
0x180008d13  call    cs:__imp_RtlReleaseResource
0x180008d19  mov     eax, esi
0x180008d1b  jmp     short loc_180008D29
0x180008d1d  mov     ecx, 3
0x180008d22  int     29h; Win8: RtlFailFast(ecx)
0x180008d24  mov     eax, 6
0x180008d29  add     rsp, 58h
0x180008d2d  pop     r15
0x180008d2f  pop     r14
0x180008d31  pop     rdi
0x180008d32  pop     rsi
0x180008d33  pop     rbp
0x180008d34  pop     rbx
0x180008d35  retn
```
