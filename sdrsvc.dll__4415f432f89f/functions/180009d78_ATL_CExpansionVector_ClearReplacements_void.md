# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180009d78`
- end: `0x180009e20`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008a9c`
- `0x180009e30`

## callees

- `0x180001560`
- `0x180009d78`

## import_xrefs

- `msvcrt!free` at `0x180009dcd`
- `msvcrt!free` at `0x180009de3`
- `msvcrt!free` at `0x180009dcd`
- `msvcrt!free` at `0x180009de3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009e19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009e19`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // edi
  void *v4; // rcx
  __int64 result; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 || (operator delete[](*(void **)(*(_QWORD *)this + 8LL * i)), i >= *((_DWORD *)this + 4)) )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180009E1FLL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v1 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180009d78  mov     [rsp+arg_0], rbx
0x180009d7d  mov     [rsp+arg_8], rsi
0x180009d82  push    rdi
0x180009d83  sub     rsp, 20h
0x180009d87  mov     eax, [rcx+10h]
0x180009d8a  mov     rbx, rcx
0x180009d8d  test    eax, eax
0x180009d8f  jle     short loc_180009DC5
0x180009d91  xor     edi, edi
0x180009d93  test    edi, edi
0x180009d95  js      short loc_180009E0A
0x180009d97  cmp     edi, eax
0x180009d99  jge     short loc_180009E0A
0x180009d9b  mov     rcx, [rbx]
0x180009d9e  movsxd  rsi, edi
0x180009da1  mov     rcx, [rcx+rsi*8]; Block
0x180009da5  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009daa  cmp     edi, [rbx+10h]
0x180009dad  jge     short loc_180009E0A
0x180009daf  mov     rcx, [rbx+8]
0x180009db3  mov     rcx, [rcx+rsi*8]; Block
0x180009db7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009dbc  mov     eax, [rbx+10h]
0x180009dbf  inc     edi
0x180009dc1  cmp     edi, eax
0x180009dc3  jl      short loc_180009D93
0x180009dc5  mov     rcx, [rbx]; Block
0x180009dc8  test    rcx, rcx
0x180009dcb  jz      short loc_180009DDA
0x180009dcd  call    cs:__imp_free
0x180009dd3  mov     qword ptr [rbx], 0
0x180009dda  mov     rcx, [rbx+8]; Block
0x180009dde  test    rcx, rcx
0x180009de1  jz      short loc_180009DF1
0x180009de3  call    cs:__imp_free
0x180009de9  mov     qword ptr [rbx+8], 0
0x180009df1  mov     rsi, [rsp+28h+arg_8]
0x180009df6  xor     eax, eax
0x180009df8  mov     dword ptr [rbx+10h], 0
0x180009dff  mov     rbx, [rsp+28h+arg_0]
0x180009e04  add     rsp, 20h
0x180009e08  pop     rdi
0x180009e09  retn
0x180009e0a  xor     r9d, r9d; lpArguments
0x180009e0d  xor     r8d, r8d; nNumberOfArguments
0x180009e10  mov     ecx, 0C000008Ch; dwExceptionCode
0x180009e15  lea     edx, [r9+1]; dwExceptionFlags
0x180009e19  call    cs:__imp_RaiseException
```
