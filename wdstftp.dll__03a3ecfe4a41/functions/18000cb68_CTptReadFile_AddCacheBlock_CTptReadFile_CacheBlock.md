# CTptReadFile::AddCacheBlock(CTptReadFile::CacheBlock *)

- ea: `0x18000cb68`
- end: `0x18000ccbb`
- name: `?AddCacheBlock@CTptReadFile@@AEAAXPEAUCacheBlock@1@@Z`
- size: `339`
- prototype: `void __fastcall(CTptReadFile *__hidden this, struct CTptReadFile::CacheBlock *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cf38`

## callees

- `0x18000a960`
- `0x18000cb68`
- `0x18003c514`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000cb78`
- `KERNEL32!EnterCriticalSection` at `0x18000cb78`
- `KERNEL32!LeaveCriticalSection` at `0x18000ccaf`
- `WDSSRV!WdsPacketFree` at `0x18000cc67`
- `WDSSRV!WdsPacketFree` at `0x18000cc67`

## string_xrefs

- `0x18000cc36`: `m_bIOCompleted`
- `0x18000cc42`: `base\eco\wds\transport\lib\tptreadfile.h`

## pseudocode

```c
void __fastcall CTptReadFile::AddCacheBlock(struct _RTL_CRITICAL_SECTION *this, struct CTptReadFile::CacheBlock *a2)
{
  __int64 v4; // r9
  __int64 v5; // rax
  _QWORD *v6; // rax
  _QWORD *OwningThread; // rdi
  _QWORD *v8; // rax
  __int64 v9; // r8

  EnterCriticalSection(this);
  if ( HIDWORD(this[3].DebugInfo) )
  {
    if ( HIDWORD(this[3].DebugInfo) == 1 )
    {
      *(_QWORD *)(this[3].SpinCount
                + 8LL * (unsigned int)(*((_QWORD *)a2 + 4) / (unsigned __int64)LODWORD(this[2].LockSemaphore))) = a2;
      ++HIDWORD(this[4].DebugInfo);
    }
  }
  else
  {
    v5 = *(_QWORD *)&this[3].LockCount;
    if ( v5 )
    {
      *((_QWORD *)a2 + 13) = 0;
      *((_QWORD *)a2 + 12) = v5;
      *(_QWORD *)(*(_QWORD *)&this[3].LockCount + 104LL) = a2;
      *(_QWORD *)&this[3].LockCount = a2;
    }
    else
    {
      this[3].OwningThread = a2;
      *(_QWORD *)&this[3].LockCount = a2;
      *((_QWORD *)a2 + 12) = 0;
      *((_QWORD *)a2 + 13) = 0;
    }
    if ( ++HIDWORD(this[3].LockSemaphore) > HIDWORD(this[2].LockSemaphore) )
    {
      v6 = *(_QWORD **)&this[3].LockCount;
      if ( v6 )
      {
        OwningThread = this[3].OwningThread;
        if ( v6 == OwningThread )
        {
          *(_QWORD *)&this[3].LockCount = 0;
          this[3].OwningThread = 0;
        }
        else
        {
          v8 = (_QWORD *)OwningThread[13];
          this[3].OwningThread = v8;
          v8[12] = 0;
        }
        --HIDWORD(this[3].LockSemaphore);
        if ( OwningThread )
        {
          if ( !*((_DWORD *)OwningThread + 18) )
            WdsAssert("base\\eco\\wds\\transport\\lib\\tptreadfile.h", 0xD1u, "m_bIOCompleted", v4, 0);
          v9 = OwningThread[7];
          if ( v9 )
            WdsPacketFree(*(_QWORD *)&lpCriticalSection[4].LockCount, 0, v9, v4);
          operator delete(OwningThread);
        }
      }
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18000cb68  mov     [rsp+arg_0], rbx
0x18000cb6d  push    rdi
0x18000cb6e  sub     rsp, 30h
0x18000cb72  mov     rdi, rdx
0x18000cb75  mov     rbx, rcx
0x18000cb78  call    cs:__imp_EnterCriticalSection
0x18000cb7f  nop     dword ptr [rax+rax+00h]
0x18000cb84  cmp     dword ptr [rbx+7Ch], 0
0x18000cb88  jnz     loc_18000CC7D
0x18000cb8e  mov     rax, [rbx+80h]
0x18000cb95  test    rax, rax
0x18000cb98  jnz     short loc_18000CBB2
0x18000cb9a  mov     [rbx+88h], rdi
0x18000cba1  mov     [rbx+80h], rdi
0x18000cba8  and     [rdi+60h], rax
0x18000cbac  and     [rdi+68h], rax
0x18000cbb0  jmp     short loc_18000CBCD
0x18000cbb2  and     qword ptr [rdi+68h], 0
0x18000cbb7  mov     [rdi+60h], rax
0x18000cbbb  mov     rax, [rbx+80h]
0x18000cbc2  mov     [rax+68h], rdi
0x18000cbc6  mov     [rbx+80h], rdi
0x18000cbcd  inc     dword ptr [rbx+94h]
0x18000cbd3  mov     eax, [rbx+6Ch]
0x18000cbd6  cmp     [rbx+94h], eax
0x18000cbdc  jbe     loc_18000CCA2
0x18000cbe2  mov     rax, [rbx+80h]
0x18000cbe9  test    rax, rax
0x18000cbec  jz      loc_18000CCA2
0x18000cbf2  mov     rdi, [rbx+88h]
0x18000cbf9  cmp     rax, rdi
0x18000cbfc  jnz     short loc_18000CC10
0x18000cbfe  and     qword ptr [rbx+80h], 0
0x18000cc06  and     qword ptr [rbx+88h], 0
0x18000cc0e  jmp     short loc_18000CC20
0x18000cc10  mov     rax, [rdi+68h]
0x18000cc14  mov     [rbx+88h], rax
0x18000cc1b  and     qword ptr [rax+60h], 0
0x18000cc20  dec     dword ptr [rbx+94h]
0x18000cc26  test    rdi, rdi
0x18000cc29  jz      short loc_18000CCA2
0x18000cc2b  cmp     dword ptr [rdi+48h], 0
0x18000cc2f  jnz     short loc_18000CC4E
0x18000cc31  and     [rsp+38h+var_18], 0
0x18000cc36  lea     r8, aMBiocompleted; "m_bIOCompleted"
0x18000cc3d  mov     edx, 0D1h; unsigned int
0x18000cc42  lea     rcx, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000cc49  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000cc4e  mov     r8, [rdi+38h]
0x18000cc52  test    r8, r8
0x18000cc55  jz      short loc_18000CC73
0x18000cc57  mov     rcx, cs:lpCriticalSection
0x18000cc5e  xor     edx, edx
0x18000cc60  mov     rcx, [rcx+0A8h]
0x18000cc67  call    cs:__imp_WdsPacketFree
0x18000cc6e  nop     dword ptr [rax+rax+00h]
0x18000cc73  mov     rcx, rdi; void *
0x18000cc76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc7b  jmp     short loc_18000CCA2
0x18000cc7d  cmp     dword ptr [rbx+7Ch], 1
0x18000cc81  jnz     short loc_18000CCA2
0x18000cc83  mov     ecx, [rbx+68h]
0x18000cc86  xor     edx, edx
0x18000cc88  mov     rax, [rdi+20h]
0x18000cc8c  div     rcx
0x18000cc8f  mov     ecx, eax
0x18000cc91  mov     rax, [rbx+98h]
0x18000cc98  mov     [rax+rcx*8], rdi
0x18000cc9c  inc     dword ptr [rbx+0A4h]
0x18000cca2  mov     rcx, rbx
0x18000cca5  mov     rbx, [rsp+38h+arg_0]
0x18000ccaa  add     rsp, 30h
0x18000ccae  pop     rdi
0x18000ccaf  jmp     cs:__imp_LeaveCriticalSection
```
