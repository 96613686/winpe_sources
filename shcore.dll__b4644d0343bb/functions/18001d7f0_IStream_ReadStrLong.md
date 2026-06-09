# IStream_ReadStrLong

- ea: `0x18001d7f0`
- end: `0x18001d92d`
- name: `IStream_ReadStrLong`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001d7f0`
- `0x18001d940`
- `0x1800672e8`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d889`

## pseudocode

```c
__int64 __fastcall IStream_ReadStrLong(__int64 *a1, void **a2)
{
  __int64 v2; // rax
  int v5; // ebx
  __int64 v6; // rsi
  unsigned int v7; // eax
  SIZE_T v8; // rax
  unsigned __int64 v9; // kr00_8
  void *v11; // rax
  size_t v12; // rax
  unsigned __int64 v13; // rsi
  __int64 v14; // rax
  void *v15; // rdx
  int v16; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+58h] [rbp+10h] BYREF
  __int64 v18; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  v2 = *a1;
  v16 = 0;
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, __int64, int *))(v2 + 24))(a1, &v17, 4, &v16);
  if ( v5 >= 0 )
  {
    if ( v16 != 4 )
      return (unsigned int)-2147467259;
    v6 = v17;
    v7 = v17 + 1;
    if ( v17 + 1 >= v17 && (v9 = v7, v8 = 2LL * v7, *a2 = 0, v18 = 0, is_mul_ok(v9, 2u)) )
    {
      v11 = CoTaskMemAlloc(v8);
      *a2 = v11;
      if ( v11 )
      {
        v12 = CTCoAllocPolicy::_CoTaskMemSize(v11);
        memset_0(*a2, 0, v12);
        v5 = 0;
      }
      else
      {
        v5 = -2147024882;
      }
      if ( v5 >= 0 )
      {
        v13 = 2 * v6;
        if ( v13 > 0xFFFFFFFF )
        {
          v5 = -2147024362;
        }
        else
        {
          v14 = *a1;
          v15 = *a2;
          LODWORD(v18) = 0;
          v5 = (*(__int64 (__fastcall **)(__int64 *, void *, _QWORD, __int64 *))(v14 + 24))(
                 a1,
                 v15,
                 (unsigned int)v13,
                 &v18);
          if ( v5 >= 0 )
          {
            if ( (_DWORD)v13 == (_DWORD)v18 )
            {
              *(_WORD *)((char *)*a2 + v13) = 0;
              return (unsigned int)v5;
            }
            v5 = -2147467259;
          }
        }
        CoTaskMemFree(*a2);
        *a2 = 0;
      }
    }
    else
    {
      return (unsigned int)-2147024362;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d7f0  mov     [rsp+arg_18], rbx
0x18001d7f5  push    rsi
0x18001d7f6  push    rdi
0x18001d7f7  push    r14
0x18001d7f9  sub     rsp, 30h
0x18001d7fd  mov     qword ptr [rdx], 0
0x18001d804  lea     r9, [rsp+48h+arg_0]
0x18001d809  mov     rax, [rcx]
0x18001d80c  mov     rdi, rdx
0x18001d80f  mov     r8d, 4
0x18001d815  mov     [rsp+48h+arg_0], 0
0x18001d81d  lea     rdx, [rsp+48h+arg_8]
0x18001d822  mov     [rsp+48h+arg_8], 0
0x18001d82a  mov     r14, rcx
0x18001d82d  mov     rax, [rax+18h]
0x18001d831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d836  mov     ebx, eax
0x18001d838  test    eax, eax
0x18001d83a  js      short loc_18001D876
0x18001d83c  cmp     [rsp+48h+arg_0], 4
0x18001d841  jnz     loc_18001D923
0x18001d847  mov     esi, [rsp+48h+arg_8]
0x18001d84b  lea     eax, [rsi+1]
0x18001d84e  cmp     eax, esi
0x18001d850  jb      short loc_18001D871
0x18001d852  mov     ecx, eax
0x18001d854  mov     eax, 2
0x18001d859  mul     rcx
0x18001d85c  mov     qword ptr [rdi], 0
0x18001d863  mov     [rsp+48h+arg_10], 0
0x18001d86c  test    rdx, rdx
0x18001d86f  jz      short loc_18001D886
0x18001d871  mov     ebx, 80070216h
0x18001d876  mov     eax, ebx
0x18001d878  mov     rbx, [rsp+48h+arg_18]
0x18001d87d  add     rsp, 30h
0x18001d881  pop     r14
0x18001d883  pop     rdi
0x18001d884  pop     rsi
0x18001d885  retn
0x18001d886  mov     rcx, rax; cb
0x18001d889  call    cs:__imp_CoTaskMemAlloc
0x18001d88f  mov     [rdi], rax
0x18001d892  test    rax, rax
0x18001d895  jz      short loc_18001D915
0x18001d897  mov     rcx, rax; void *
0x18001d89a  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001d89f  mov     rcx, [rdi]; void *
0x18001d8a2  mov     r8, rax; Size
0x18001d8a5  xor     edx, edx; Val
0x18001d8a7  call    memset_0
0x18001d8ac  xor     ebx, ebx
0x18001d8ae  test    ebx, ebx
0x18001d8b0  js      short loc_18001D876
0x18001d8b2  add     rsi, rsi
0x18001d8b5  mov     eax, 0FFFFFFFFh
0x18001d8ba  cmp     rsi, rax
0x18001d8bd  ja      short loc_18001D8FB
0x18001d8bf  mov     rax, [r14]
0x18001d8c2  lea     r9, [rsp+48h+arg_10]
0x18001d8c7  mov     rdx, [rdi]
0x18001d8ca  mov     r8d, esi
0x18001d8cd  mov     rcx, r14
0x18001d8d0  mov     dword ptr [rsp+48h+arg_10], 0
0x18001d8d8  mov     rax, [rax+18h]
0x18001d8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8e1  mov     ebx, eax
0x18001d8e3  test    eax, eax
0x18001d8e5  js      short loc_18001D900
0x18001d8e7  cmp     esi, dword ptr [rsp+48h+arg_10]
0x18001d8eb  jnz     short loc_18001D91C
0x18001d8ed  mov     rcx, [rdi]
0x18001d8f0  xor     eax, eax
0x18001d8f2  mov     [rsi+rcx], ax
0x18001d8f6  jmp     loc_18001D876
0x18001d8fb  mov     ebx, 80070216h
0x18001d900  mov     rcx, [rdi]; pv
0x18001d903  call    cs:__imp_CoTaskMemFree
0x18001d909  mov     qword ptr [rdi], 0
0x18001d910  jmp     loc_18001D876
0x18001d915  mov     ebx, 8007000Eh
0x18001d91a  jmp     short loc_18001D8AE
0x18001d91c  mov     ebx, 80004005h
0x18001d921  jmp     short loc_18001D900
0x18001d923  mov     ebx, 80004005h
0x18001d928  jmp     loc_18001D876
```
