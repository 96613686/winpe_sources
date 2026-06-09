# CImpReg::Free(int,CHandleCache *)

- ea: `0x180008830`
- end: `0x1800088e9`
- name: `?Free@CImpReg@@QEAAXHPEAVCHandleCache@@@Z`
- size: `185`
- prototype: `void __fastcall(void (**this)(void), int, struct CHandleCache *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002770`

## callees

- `0x180008830`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000887a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000887a`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x1800088bd`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x1800088bd`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000885c`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008896`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000885c`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008896`

## pseudocode

```c
void __fastcall CImpReg::Free(void (**this)(void), int a2, struct CHandleCache *a3)
{
  int i; // ebx
  void *v7; // rax
  HKEY v8; // rcx
  int j; // ebx
  void (__fastcall ***v10)(void *, __int64); // rax

  for ( i = *((_DWORD *)a3 + 2) - 1; i >= a2; --i )
  {
    if ( i < *((_DWORD *)a3 + 2) )
    {
      v7 = CFlexArray::GetAt((struct CHandleCache *)((char *)a3 + 8), i);
      if ( v7 )
      {
        v8 = (HKEY)*((_QWORD *)v7 + 3);
        if ( v8 )
        {
          if ( !this[16] || *((_DWORD *)a3 + 24) )
            RegCloseKey(v8);
          else
            this[18]();
        }
      }
    }
  }
  for ( j = *((_DWORD *)a3 + 2) - 1; j >= a2; --j )
  {
    v10 = (void (__fastcall ***)(void *, __int64))CFlexArray::GetAt((struct CHandleCache *)((char *)a3 + 8), j);
    if ( v10 )
      (**v10)(v10, 1);
    CFlexArray::RemoveAt((struct CHandleCache *)((char *)a3 + 8), j);
  }
}

```

## disassembly

```asm
0x180008830  push    rbx
0x180008832  push    rbp
0x180008833  push    rsi
0x180008834  push    rdi
0x180008835  push    r14
0x180008837  sub     rsp, 20h
0x18000883b  mov     ebx, [r8+8]
0x18000883f  mov     r14, r8
0x180008842  dec     ebx
0x180008844  mov     esi, edx
0x180008846  mov     rbp, rcx
0x180008849  cmp     ebx, edx
0x18000884b  jl      short loc_180008886
0x18000884d  nop     dword ptr [rax]
0x180008850  cmp     ebx, [r14+8]
0x180008854  jge     short loc_180008880
0x180008856  mov     edx, ebx
0x180008858  lea     rcx, [r14+8]
0x18000885c  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180008862  test    rax, rax
0x180008865  jz      short loc_180008880
0x180008867  mov     rcx, [rax+18h]; hKey
0x18000886b  test    rcx, rcx
0x18000886e  jz      short loc_180008880
0x180008870  cmp     qword ptr [rbp+80h], 0
0x180008878  jnz     short loc_1800088D4
0x18000887a  call    cs:__imp_RegCloseKey
0x180008880  dec     ebx
0x180008882  cmp     ebx, esi
0x180008884  jge     short loc_180008850
0x180008886  mov     ebx, [r14+8]
0x18000888a  dec     ebx
0x18000888c  cmp     ebx, esi
0x18000888e  jl      short loc_1800088C9
0x180008890  mov     edx, ebx
0x180008892  lea     rcx, [r14+8]
0x180008896  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000889c  mov     r8, rax
0x18000889f  test    rax, rax
0x1800088a2  jz      short loc_1800088B7
0x1800088a4  mov     rcx, [rax]
0x1800088a7  mov     edx, 1
0x1800088ac  mov     rax, [rcx]
0x1800088af  mov     rcx, r8
0x1800088b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b7  mov     edx, ebx
0x1800088b9  lea     rcx, [r14+8]
0x1800088bd  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x1800088c3  dec     ebx
0x1800088c5  cmp     ebx, esi
0x1800088c7  jge     short loc_180008890
0x1800088c9  add     rsp, 20h
0x1800088cd  pop     r14
0x1800088cf  pop     rdi
0x1800088d0  pop     rsi
0x1800088d1  pop     rbp
0x1800088d2  pop     rbx
0x1800088d3  retn
0x1800088d4  cmp     dword ptr [r14+60h], 0
0x1800088d9  jnz     short loc_18000887A
0x1800088db  mov     rax, [rbp+90h]
0x1800088e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e7  jmp     short loc_180008880
```
