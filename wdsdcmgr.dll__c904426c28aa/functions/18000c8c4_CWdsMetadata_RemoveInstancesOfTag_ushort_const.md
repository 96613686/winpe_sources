# CWdsMetadata::RemoveInstancesOfTag(ushort const *)

- ea: `0x18000c8c4`
- end: `0x18000c9f8`
- name: `?RemoveInstancesOfTag@CWdsMetadata@@QEAAKPEBG@Z`
- size: `308`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800042f4`
- `0x1800062f0`
- `0x18000f210`

## callees

- `0x18000a7ec`
- `0x18000ac50`
- `0x18000c8c4`
- `0x180014d58`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveInstancesOfTag(CWdsMetadata *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rbp
  int GroupIndex; // eax
  const char *v6; // rdx
  unsigned int v7; // r9d
  unsigned int i; // ecx
  int v9; // ecx
  unsigned int v10; // r12d
  __int64 v11; // r15
  const char *v12; // rdx
  unsigned int v13; // esi
  __int64 v14; // r14
  const char *v15; // rdx

  v2 = 0;
  v3 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex(this, this, a2);
  if ( GroupIndex >= 0 )
  {
    if ( (unsigned int)GroupIndex < *((_DWORD *)this + 3) )
    {
      _mm_lfence();
      v3 = *(_QWORD *)(*(_QWORD *)this + 8LL * (unsigned int)GroupIndex);
    }
    else
    {
      v2 = 1413;
    }
    v7 = 5165;
    for ( i = v2;
          !ElValidateWin32(i, v6, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", v7) && *(_DWORD *)(v3 + 20);
          i = v2 )
    {
      v9 = *(_DWORD *)(v3 + 20);
      v10 = -1;
      v11 = 0;
      if ( v9 )
        v11 = **(_QWORD **)(v3 + 8);
      v2 = 1413;
      if ( v9 )
        v2 = 0;
      if ( ElValidateWin32(v2, v15, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1435u) )
        break;
      v13 = 0;
      if ( *((_DWORD *)this + 15) )
      {
        do
        {
          v14 = 0;
          v2 = 0;
          if ( v13 < *((_DWORD *)this + 15) )
            v14 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v13);
          else
            v2 = 1413;
          if ( ElValidateWin32(v2, v12, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x143Cu) )
            return v2;
          if ( v14 == v11 )
          {
            v10 = v13;
            break;
          }
        }
        while ( ++v13 < *((_DWORD *)this + 15) );
      }
      v2 = CWdsMetadata::RemoveEntry(this, (const char *)v10);
      v7 = 5190;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000c8c4  mov     [rsp+arg_0], rbx
0x18000c8c9  mov     [rsp+arg_8], rbp
0x18000c8ce  mov     [rsp+arg_10], rsi
0x18000c8d3  push    rdi
0x18000c8d4  push    r12
0x18000c8d6  push    r13
0x18000c8d8  push    r14
0x18000c8da  push    r15
0x18000c8dc  sub     rsp, 20h
0x18000c8e0  xor     r13d, r13d
0x18000c8e3  mov     r8, rdx
0x18000c8e6  mov     rdx, rcx
0x18000c8e9  mov     ebx, r13d
0x18000c8ec  mov     ebp, r13d
0x18000c8ef  mov     rdi, rcx
0x18000c8f2  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000c8f7  test    eax, eax
0x18000c8f9  js      loc_18000C9D9
0x18000c8ff  cmp     eax, [rdi+0Ch]
0x18000c902  jb      short loc_18000C90B
0x18000c904  mov     ebx, 585h
0x18000c909  jmp     short loc_18000C917
0x18000c90b  lfence
0x18000c90e  mov     ecx, eax
0x18000c910  mov     rax, [rdi]
0x18000c913  mov     rbp, [rax+rcx*8]
0x18000c917  mov     r9d, 142Dh
0x18000c91d  mov     ecx, ebx
0x18000c91f  jmp     loc_18000C9BF
0x18000c924  mov     ecx, [rbp+14h]
0x18000c927  or      r12d, 0FFFFFFFFh
0x18000c92b  mov     r15, r13
0x18000c92e  test    ecx, ecx
0x18000c930  jz      short loc_18000C939
0x18000c932  mov     rax, [rbp+8]
0x18000c936  mov     r15, [rax]
0x18000c939  test    ecx, ecx
0x18000c93b  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c942  mov     ebx, 585h
0x18000c947  mov     r9d, 1435h; unsigned int
0x18000c94d  cmovnz  ebx, r13d
0x18000c951  mov     ecx, ebx; unsigned int
0x18000c953  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c958  test    eax, eax
0x18000c95a  jnz     short loc_18000C9D9
0x18000c95c  mov     esi, r13d
0x18000c95f  cmp     [rdi+3Ch], r13d
0x18000c963  jbe     short loc_18000C9AA
0x18000c965  mov     r14, r13
0x18000c968  mov     ebx, r13d
0x18000c96b  cmp     esi, [rdi+3Ch]
0x18000c96e  jb      short loc_18000C977
0x18000c970  mov     ebx, 585h
0x18000c975  jmp     short loc_18000C981
0x18000c977  mov     rax, [rdi+30h]
0x18000c97b  mov     ecx, esi
0x18000c97d  mov     r14, [rax+rcx*8]
0x18000c981  mov     r9d, 143Ch; unsigned int
0x18000c987  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c98e  mov     ecx, ebx; unsigned int
0x18000c990  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c995  test    eax, eax
0x18000c997  jnz     short loc_18000C9D9
0x18000c999  cmp     r14, r15
0x18000c99c  jz      short loc_18000C9A7
0x18000c99e  inc     esi
0x18000c9a0  cmp     esi, [rdi+3Ch]
0x18000c9a3  jb      short loc_18000C965
0x18000c9a5  jmp     short loc_18000C9AA
0x18000c9a7  mov     r12d, esi
0x18000c9aa  mov     edx, r12d; unsigned int
0x18000c9ad  mov     rcx, rdi; this
0x18000c9b0  call    ?RemoveEntry@CWdsMetadata@@QEAAKK@Z; CWdsMetadata::RemoveEntry(ulong)
0x18000c9b5  mov     ebx, eax
0x18000c9b7  mov     r9d, 1446h; unsigned int
0x18000c9bd  mov     ecx, eax; unsigned int
0x18000c9bf  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000c9c6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c9cb  test    eax, eax
0x18000c9cd  jnz     short loc_18000C9D9
0x18000c9cf  cmp     [rbp+14h], r13d
0x18000c9d3  jnz     loc_18000C924
0x18000c9d9  mov     rbp, [rsp+48h+arg_8]
0x18000c9de  mov     eax, ebx
0x18000c9e0  mov     rbx, [rsp+48h+arg_0]
0x18000c9e5  mov     rsi, [rsp+48h+arg_10]
0x18000c9ea  add     rsp, 20h
0x18000c9ee  pop     r15
0x18000c9f0  pop     r14
0x18000c9f2  pop     r13
0x18000c9f4  pop     r12
0x18000c9f6  pop     rdi
0x18000c9f7  retn
```
