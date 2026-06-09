# CWdsComMetadataBuilder::get_TagCount(ulong *)

- ea: `0x18000ea90`
- end: `0x18000eb3b`
- name: `?get_TagCount@CWdsComMetadataBuilder@@UEAAJPEAK@Z`
- size: `171`
- prototype: `__int64 __fastcall(CWdsComMetadataBuilder *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ea90`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000eab7`
- `KERNEL32!EnterCriticalSection` at `0x18000eab7`
- `KERNEL32!LeaveCriticalSection` at `0x18000eb1d`
- `KERNEL32!LeaveCriticalSection` at `0x18000eb1d`

## string_xrefs

- `0x18000eac7`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::get_TagCount(CWdsComMetadataBuilder *this, unsigned int *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  const char *v6; // rdx
  unsigned int v7; // ecx
  unsigned int v8; // edx
  unsigned int v9; // r8d
  __int64 v10; // r9
  __int64 v11; // r10
  unsigned int v12; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a2
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x1EDu) >= 0) )
  {
    v7 = *((_DWORD *)this + 19);
    v8 = 0;
    v9 = 0;
    if ( v7 )
    {
      v10 = 0;
      do
      {
        v11 = 0;
        if ( v9 < v7 )
          v11 = *(_QWORD *)(v10 + *((_QWORD *)this + 8));
        v12 = v8 + 1;
        if ( !*(_DWORD *)(v11 + 20) )
          v12 = v8;
        ++v9;
        v10 += 8;
        v8 = v12;
      }
      while ( v9 < v7 );
    }
    *a2 = v8;
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18000ea90  mov     [rsp+arg_0], rbx
0x18000ea95  mov     [rsp+arg_8], rsi
0x18000ea9a  mov     [rsp+arg_10], rdi
0x18000ea9f  push    r14
0x18000eaa1  sub     rsp, 20h
0x18000eaa5  lea     rsi, [rcx+88h]
0x18000eaac  mov     rdi, rcx
0x18000eaaf  mov     rcx, rsi; lpCriticalSection
0x18000eab2  mov     r14, rdx
0x18000eab5  xor     ebx, ebx
0x18000eab7  call    cs:__imp_EnterCriticalSection
0x18000eabd  test    r14, r14
0x18000eac0  jnz     short loc_18000EADF
0x18000eac2  mov     ebx, 80070057h
0x18000eac7  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000eace  mov     ecx, ebx; int
0x18000ead0  mov     r9d, 1EDh; unsigned int
0x18000ead6  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000eadb  test    eax, eax
0x18000eadd  js      short loc_18000EB1A
0x18000eadf  mov     ecx, [rdi+4Ch]
0x18000eae2  xor     edx, edx
0x18000eae4  xor     r8d, r8d
0x18000eae7  test    ecx, ecx
0x18000eae9  jz      short loc_18000EB17
0x18000eaeb  xor     r9d, r9d
0x18000eaee  xor     r10d, r10d
0x18000eaf1  cmp     r8d, ecx
0x18000eaf4  jnb     short loc_18000EAFE
0x18000eaf6  mov     rax, [rdi+40h]
0x18000eafa  mov     r10, [r9+rax]
0x18000eafe  cmp     dword ptr [r10+14h], 0
0x18000eb03  lea     eax, [rdx+1]
0x18000eb06  cmovbe  eax, edx
0x18000eb09  inc     r8d
0x18000eb0c  add     r9, 8
0x18000eb10  mov     edx, eax
0x18000eb12  cmp     r8d, ecx
0x18000eb15  jb      short loc_18000EAEE
0x18000eb17  mov     [r14], edx
0x18000eb1a  mov     rcx, rsi; lpCriticalSection
0x18000eb1d  call    cs:__imp_LeaveCriticalSection
0x18000eb23  mov     rsi, [rsp+28h+arg_8]
0x18000eb28  mov     eax, ebx
0x18000eb2a  mov     rbx, [rsp+28h+arg_0]
0x18000eb2f  mov     rdi, [rsp+28h+arg_10]
0x18000eb34  add     rsp, 20h
0x18000eb38  pop     r14
0x18000eb3a  retn
```
