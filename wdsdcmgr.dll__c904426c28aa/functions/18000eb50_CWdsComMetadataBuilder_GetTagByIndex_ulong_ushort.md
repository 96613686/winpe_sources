# CWdsComMetadataBuilder::GetTagByIndex(ulong,ushort * *)

- ea: `0x18000eb50`
- end: `0x18000ec89`
- name: `?GetTagByIndex@CWdsComMetadataBuilder@@UEAAJKPEAPEAG@Z`
- size: `313`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000eb50`
- `0x18001381c`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000eb81`
- `KERNEL32!EnterCriticalSection` at `0x18000eb81`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec64`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec64`

## string_xrefs

- `0x18000eb91`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ec1a`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ec51`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::GetTagByIndex(CWdsComMetadataBuilder *this, int a2, unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r15
  const unsigned __int16 *v7; // r12
  const char *v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // r14
  __int64 v12; // rbx
  unsigned int v13; // edi
  const char *v14; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( a3
    || (v9 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x219u) >= 0) )
  {
    v10 = *((_DWORD *)this + 19);
    v11 = 0;
    v12 = 0;
    if ( v10 )
    {
      while ( 1 )
      {
        v13 = 0;
        if ( (unsigned int)v12 < v10 )
          v11 = *(_QWORD *)(*((_QWORD *)this + 8) + 8 * v12);
        else
          v13 = 1413;
        if ( ElValidateWin32(v13, v8, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xE5Du) )
          break;
        if ( *(_DWORD *)(v11 + 20) )
        {
          if ( !a2 )
          {
            v7 = *(const unsigned __int16 **)v11;
            break;
          }
          --a2;
        }
        v10 = *((_DWORD *)this + 19);
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= v10 )
          goto LABEL_12;
      }
    }
    else
    {
LABEL_12:
      v13 = 1413;
      ElValidateWin32(0x585u, v8, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xE6Eu);
    }
    if ( ElValidateWin32(v13, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x21Du) )
    {
      v9 = v13 | 0x80070000;
      if ( !v13 )
        v9 = 0;
    }
    else
    {
      v9 = SysAllocStringHr(v7, a3);
      ElValidateHr(v9, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x220u);
    }
  }
  LeaveCriticalSection(v3);
  return v9;
}

```

## disassembly

```asm
0x18000eb50  mov     [rsp+arg_0], rbx
0x18000eb55  mov     [rsp+arg_8], rbp
0x18000eb5a  mov     [rsp+arg_10], rsi
0x18000eb5f  push    rdi
0x18000eb60  push    r12
0x18000eb62  push    r13
0x18000eb64  push    r14
0x18000eb66  push    r15
0x18000eb68  sub     rsp, 20h
0x18000eb6c  lea     r15, [rcx+88h]
0x18000eb73  mov     rsi, rcx
0x18000eb76  mov     rcx, r15; lpCriticalSection
0x18000eb79  mov     r13, r8
0x18000eb7c  mov     ebp, edx
0x18000eb7e  xor     r12d, r12d
0x18000eb81  call    cs:__imp_EnterCriticalSection
0x18000eb87  test    r13, r13
0x18000eb8a  jnz     short loc_18000EBAD
0x18000eb8c  mov     ebx, 80070057h
0x18000eb91  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000eb98  mov     ecx, ebx; int
0x18000eb9a  mov     r9d, 219h; unsigned int
0x18000eba0  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000eba5  test    eax, eax
0x18000eba7  js      loc_18000EC61
0x18000ebad  mov     eax, [rsi+4Ch]
0x18000ebb0  xor     r14d, r14d
0x18000ebb3  xor     ebx, ebx
0x18000ebb5  test    eax, eax
0x18000ebb7  jz      short loc_18000EBFB
0x18000ebb9  xor     edi, edi
0x18000ebbb  cmp     ebx, eax
0x18000ebbd  jb      short loc_18000EBC6
0x18000ebbf  mov     edi, 585h
0x18000ebc4  jmp     short loc_18000EBCE
0x18000ebc6  mov     rax, [rsi+40h]
0x18000ebca  mov     r14, [rax+rbx*8]
0x18000ebce  mov     r9d, 0E5Dh; unsigned int
0x18000ebd4  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000ebdb  mov     ecx, edi; unsigned int
0x18000ebdd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ebe2  test    eax, eax
0x18000ebe4  jnz     short loc_18000EC14
0x18000ebe6  cmp     [r14+14h], r12d
0x18000ebea  jbe     short loc_18000EBF2
0x18000ebec  test    ebp, ebp
0x18000ebee  jz      short loc_18000EC3B
0x18000ebf0  dec     ebp
0x18000ebf2  mov     eax, [rsi+4Ch]
0x18000ebf5  inc     ebx
0x18000ebf7  cmp     ebx, eax
0x18000ebf9  jb      short loc_18000EBB9
0x18000ebfb  mov     edi, 585h
0x18000ec00  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000ec07  mov     ecx, edi; unsigned int
0x18000ec09  mov     r9d, 0E6Eh; unsigned int
0x18000ec0f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ec14  mov     r9d, 21Dh; unsigned int
0x18000ec1a  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ec21  mov     ecx, edi; unsigned int
0x18000ec23  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ec28  test    eax, eax
0x18000ec2a  jz      short loc_18000EC40
0x18000ec2c  mov     ebx, edi
0x18000ec2e  or      ebx, 80070000h
0x18000ec34  test    edi, edi
0x18000ec36  cmovz   ebx, edi
0x18000ec39  jmp     short loc_18000EC61
0x18000ec3b  mov     r12, [r14]
0x18000ec3e  jmp     short loc_18000EC14
0x18000ec40  mov     rdx, r13; unsigned __int16 **
0x18000ec43  mov     rcx, r12; unsigned __int16 *
0x18000ec46  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x18000ec4b  mov     r9d, 220h; unsigned int
0x18000ec51  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ec58  mov     ecx, eax; int
0x18000ec5a  mov     ebx, eax
0x18000ec5c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ec61  mov     rcx, r15; lpCriticalSection
0x18000ec64  call    cs:__imp_LeaveCriticalSection
0x18000ec6a  mov     rbp, [rsp+48h+arg_8]
0x18000ec6f  mov     eax, ebx
0x18000ec71  mov     rbx, [rsp+48h+arg_0]
0x18000ec76  mov     rsi, [rsp+48h+arg_10]
0x18000ec7b  add     rsp, 20h
0x18000ec7f  pop     r15
0x18000ec81  pop     r14
0x18000ec83  pop     r13
0x18000ec85  pop     r12
0x18000ec87  pop     rdi
0x18000ec88  retn
```
