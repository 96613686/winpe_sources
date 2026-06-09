# CImpReg::EndBatch(long,IWbemClassObject *,CObject *,int)

- ea: `0x1800092f0`
- end: `0x1800093cf`
- name: `?EndBatch@CImpReg@@UEAAXJPEAUIWbemClassObject@@PEAVCObject@@H@Z`
- size: `223`
- prototype: `void __fastcall(void (**this)(void), __int64, struct IWbemClassObject *, struct CObject *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800092f0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009349`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009349`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000938e`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000938e`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000932b`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180009367`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000932b`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180009367`

## pseudocode

```c
void __fastcall CImpReg::EndBatch(void (**this)(void), __int64 a2, struct IWbemClassObject *a3, struct CObject *a4)
{
  int i; // esi
  void *v7; // rax
  HKEY v8; // rcx
  int j; // edi
  void (__fastcall ***v10)(void *, __int64); // rax

  if ( a4 )
  {
    for ( i = *((_DWORD *)a4 + 2) - 1; i >= 0; --i )
    {
      if ( i < *((_DWORD *)a4 + 2) )
      {
        v7 = CFlexArray::GetAt((struct CObject *)((char *)a4 + 8), i);
        if ( v7 )
        {
          v8 = (HKEY)*((_QWORD *)v7 + 3);
          if ( v8 )
          {
            if ( !this[16] || *((_DWORD *)a4 + 24) )
              RegCloseKey(v8);
            else
              this[18]();
          }
        }
      }
    }
    for ( j = *((_DWORD *)a4 + 2) - 1; j >= 0; --j )
    {
      v10 = (void (__fastcall ***)(void *, __int64))CFlexArray::GetAt((struct CObject *)((char *)a4 + 8), j);
      if ( v10 )
        (**v10)(v10, 1);
      CFlexArray::RemoveAt((struct CObject *)((char *)a4 + 8), j);
    }
    (**(void (__fastcall ***)(struct CObject *, __int64, struct IWbemClassObject *))a4)(a4, 1, a3);
  }
}

```

## disassembly

```asm
0x1800092f0  test    r9, r9
0x1800092f3  jnz     short loc_1800092F6
0x1800092f5  retn
0x1800092f6  mov     [rsp+arg_10], rbx
0x1800092fb  push    rdi
0x1800092fc  sub     rsp, 20h
0x180009300  mov     [rsp+28h+arg_0], rsi
0x180009305  mov     rbx, r9
0x180009308  mov     esi, [r9+8]
0x18000930c  mov     rdi, rcx
0x18000930f  sub     esi, 1
0x180009312  mov     [rsp+28h+arg_8], r14
0x180009317  js      short loc_180009354
0x180009319  nop     dword ptr [rax+00000000h]
0x180009320  cmp     esi, [rbx+8]
0x180009323  jge     short loc_18000934F
0x180009325  mov     edx, esi
0x180009327  lea     rcx, [rbx+8]
0x18000932b  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180009331  test    rax, rax
0x180009334  jz      short loc_18000934F
0x180009336  mov     rcx, [rax+18h]; hKey
0x18000933a  test    rcx, rcx
0x18000933d  jz      short loc_18000934F
0x18000933f  cmp     qword ptr [rdi+80h], 0
0x180009347  jnz     short loc_1800093BB
0x180009349  call    cs:__imp_RegCloseKey
0x18000934f  sub     esi, 1
0x180009352  jns     short loc_180009320
0x180009354  mov     edi, [rbx+8]
0x180009357  sub     edi, 1
0x18000935a  mov     rsi, [rsp+28h+arg_0]
0x18000935f  js      short loc_180009399
0x180009361  mov     edx, edi
0x180009363  lea     rcx, [rbx+8]
0x180009367  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000936d  mov     r8, rax
0x180009370  test    rax, rax
0x180009373  jz      short loc_180009388
0x180009375  mov     rcx, [rax]
0x180009378  mov     edx, 1
0x18000937d  mov     rax, [rcx]
0x180009380  mov     rcx, r8
0x180009383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009388  mov     edx, edi
0x18000938a  lea     rcx, [rbx+8]
0x18000938e  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180009394  sub     edi, 1
0x180009397  jns     short loc_180009361
0x180009399  mov     rax, [rbx]
0x18000939c  mov     edx, 1
0x1800093a1  mov     rcx, rbx
0x1800093a4  mov     rax, [rax]
0x1800093a7  mov     r14, [rsp+28h+arg_8]
0x1800093ac  mov     rbx, [rsp+28h+arg_10]
0x1800093b1  add     rsp, 20h
0x1800093b5  pop     rdi
0x1800093b6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800093bb  cmp     dword ptr [rbx+60h], 0
0x1800093bf  jnz     short loc_180009349
0x1800093c1  mov     rax, [rdi+90h]
0x1800093c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093cd  jmp     short loc_18000934F
```
