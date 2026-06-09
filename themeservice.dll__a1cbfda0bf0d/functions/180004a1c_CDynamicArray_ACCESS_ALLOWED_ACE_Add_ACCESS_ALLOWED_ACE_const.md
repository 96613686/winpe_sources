# CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(_ACCESS_ALLOWED_ACE * const &)

- ea: `0x180004a1c`
- end: `0x180004b1a`
- name: `?Add@?$CDynamicArray@PEAU_ACCESS_ALLOWED_ACE@@@@QEAAJAEBQEAU_ACCESS_ALLOWED_ACE@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(unsigned int *, _QWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003280`
- `0x180003790`
- `0x18000461c`
- `0x180004980`

## callees

- `0x180004a1c`
- `0x180005fb4`
- `0x180006194`
- `0x18000f9c2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ae5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ae5`

## pseudocode

```c
__int64 __fastcall CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(unsigned int *a1, _QWORD *a2)
{
  void **v2; // rsi
  unsigned int v5; // ebp
  void *v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // edx
  void *v10; // rcx
  __int64 v11; // r8
  void *v12; // rdx
  void *v13; // rbx
  unsigned __int64 v15; // [rsp+40h] [rbp+8h] BYREF
  void *v16; // [rsp+50h] [rbp+18h] BYREF

  v2 = (void **)(a1 + 2);
  v5 = -1073741801;
  if ( *((_QWORD *)a1 + 1) )
    goto LABEL_5;
  *a1 = 0;
  v15 = 0;
  a1[1] = 16;
  *v2 = 0;
  if ( (int)ULongLongMult(0x10u, (unsigned __int64)a2, &v15) >= 0 )
    CTLocalAllocPolicy::Alloc(v6, (unsigned int)a2, v15, v2);
  if ( *v2 )
  {
LABEL_5:
    v7 = a1[1];
    if ( *a1 == v7 )
    {
      v8 = v7 + 16;
      if ( v7 + 16 >= v7 )
      {
        v16 = 0;
        v15 = 0;
        if ( (int)ULongLongMult(v8, (unsigned __int64)a2, &v15) >= 0
          && CTLocalAllocPolicy::Alloc(v10, v9, v15, &v16) >= 0 )
        {
          v11 = *a1;
          v12 = *v2;
          a1[1] = v8;
          v13 = v16;
          memcpy_0(v16, v12, 8 * v11);
          LocalFree(*v2);
          *v2 = v13;
        }
      }
    }
    if ( *a1 < a1[1] )
    {
      *((_QWORD *)*v2 + (*a1)++) = *a2;
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180004a1c  mov     rax, rsp
0x180004a1f  mov     [rax+10h], rbx
0x180004a23  mov     [rax+20h], rbp
0x180004a27  push    rsi
0x180004a28  push    rdi
0x180004a29  push    r14
0x180004a2b  sub     rsp, 20h
0x180004a2f  lea     rsi, [rcx+8]
0x180004a33  mov     r14, rdx
0x180004a36  cmp     qword ptr [rsi], 0
0x180004a3a  mov     rdi, rcx
0x180004a3d  mov     ebp, 0C0000017h
0x180004a42  jnz     short loc_180004A85
0x180004a44  mov     dword ptr [rcx], 0
0x180004a4a  lea     r8, [rax+8]; unsigned __int64 *
0x180004a4e  mov     ecx, 10h; unsigned __int64
0x180004a53  mov     qword ptr [rax+8], 0
0x180004a5b  mov     [rdi+4], ecx
0x180004a5e  mov     qword ptr [rsi], 0
0x180004a65  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180004a6a  test    eax, eax
0x180004a6c  js      short loc_180004A7B
0x180004a6e  mov     r8, [rsp+38h+arg_0]; unsigned __int64
0x180004a73  mov     r9, rsi; void **
0x180004a76  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180004a7b  cmp     qword ptr [rsi], 0
0x180004a7f  jz      loc_180004B05
0x180004a85  mov     eax, [rdi+4]
0x180004a88  cmp     [rdi], eax
0x180004a8a  jnz     short loc_180004AEE
0x180004a8c  lea     ebx, [rax+10h]
0x180004a8f  cmp     ebx, eax
0x180004a91  jb      short loc_180004AEE
0x180004a93  mov     ecx, ebx; unsigned __int64
0x180004a95  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x180004a9a  mov     [rsp+38h+arg_10], 0
0x180004aa3  mov     [rsp+38h+arg_0], 0
0x180004aac  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180004ab1  test    eax, eax
0x180004ab3  js      short loc_180004AEE
0x180004ab5  mov     r8, [rsp+38h+arg_0]; unsigned __int64
0x180004aba  lea     r9, [rsp+38h+arg_10]; void **
0x180004abf  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180004ac4  test    eax, eax
0x180004ac6  js      short loc_180004AEE
0x180004ac8  mov     r8d, [rdi]
0x180004acb  mov     rdx, [rsi]; Src
0x180004ace  mov     [rdi+4], ebx
0x180004ad1  mov     rbx, [rsp+38h+arg_10]
0x180004ad6  mov     rcx, rbx; void *
0x180004ad9  shl     r8, 3; Size
0x180004add  call    memcpy_0
0x180004ae2  mov     rcx, [rsi]; hMem
0x180004ae5  call    cs:__imp_LocalFree
0x180004aeb  mov     [rsi], rbx
0x180004aee  mov     eax, [rdi]
0x180004af0  cmp     eax, [rdi+4]
0x180004af3  jnb     short loc_180004B05
0x180004af5  mov     rcx, [rsi]
0x180004af8  mov     edx, eax
0x180004afa  mov     rax, [r14]
0x180004afd  mov     [rcx+rdx*8], rax
0x180004b01  inc     dword ptr [rdi]
0x180004b03  xor     ebp, ebp
0x180004b05  mov     rbx, [rsp+38h+arg_8]
0x180004b0a  mov     eax, ebp
0x180004b0c  mov     rbp, [rsp+38h+arg_18]
0x180004b11  add     rsp, 20h
0x180004b15  pop     r14
0x180004b17  pop     rdi
0x180004b18  pop     rsi
0x180004b19  retn
```
