# CVolumeEnumerator::GetNextVolume(void)

- ea: `0x180006600`
- end: `0x1800066b4`
- name: `?GetNextVolume@CVolumeEnumerator@@QEAAPEAVCVolume@@XZ`
- size: `180`
- prototype: `struct CVolume *__fastcall(LPCRITICAL_SECTION *this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180005590`
- `0x180005660`
- `0x18000747c`
- `0x180007c08`
- `0x18000bd24`
- `0x18000c968`
- `0x18000d318`
- `0x18000d4dc`
- `0x18000d5e4`
- `0x18000f744`

## callees

- `0x180006600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000662f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000662f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006689`

## pseudocode

```c
struct CVolume *__fastcall CVolumeEnumerator::GetNextVolume(LPCRITICAL_SECTION *this)
{
  __int64 v2; // rdi
  LPCRITICAL_SECTION *v3; // rsi
  _QWORD *p_Type; // rcx
  LPCRITICAL_SECTION v5; // rax

  if ( !*this )
    return 0;
  v2 = 0;
  v3 = this + 1;
  EnterCriticalSection(this[1]);
  p_Type = &(*this)->DebugInfo->Type;
  if ( p_Type )
  {
    v5 = this[2];
    if ( v5 )
    {
      while ( p_Type )
      {
        if ( p_Type > (_QWORD *)v5 )
          goto LABEL_4;
        p_Type = (_QWORD *)p_Type[1];
      }
    }
    else
    {
LABEL_4:
      v2 = *p_Type;
      this[2] = (LPCRITICAL_SECTION)p_Type;
    }
  }
  else
  {
    v2 = 0;
  }
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  LeaveCriticalSection(*v3);
  return (struct CVolume *)v2;
}

```

## disassembly

```asm
0x180006600  mov     [rsp+arg_8], rbx
0x180006605  mov     [rsp+arg_10], rsi
0x18000660a  push    rdi
0x18000660b  sub     rsp, 30h
0x18000660f  mov     rbx, rcx
0x180006612  cmp     qword ptr [rcx], 0
0x180006616  jz      loc_1800066A2
0x18000661c  xor     edi, edi
0x18000661e  mov     [rsp+38h+var_18], rdi
0x180006623  lea     rsi, [rcx+8]
0x180006627  mov     [rsp+38h+arg_0], rsi
0x18000662c  mov     rcx, [rsi]; lpCriticalSection
0x18000662f  call    cs:__imp_EnterCriticalSection
0x180006635  nop
0x180006636  mov     rax, [rbx]
0x180006639  mov     rcx, [rax]
0x18000663c  test    rcx, rcx
0x18000663f  jz      short loc_180006671
0x180006641  mov     rax, [rbx+10h]
0x180006645  test    rax, rax
0x180006648  jnz     short loc_180006661
0x18000664a  mov     rdi, [rcx]
0x18000664d  mov     [rsp+38h+var_18], rdi
0x180006652  mov     [rbx+10h], rcx
0x180006656  test    rdi, rdi
0x180006659  jz      short loc_18000667A
0x18000665b  lock inc dword ptr [rdi+8]
0x18000665f  jmp     short loc_18000667A
0x180006661  test    rcx, rcx
0x180006664  jz      short loc_180006656
0x180006666  cmp     rcx, rax
0x180006669  ja      short loc_18000664A
0x18000666b  mov     rcx, [rcx+8]
0x18000666f  jmp     short loc_180006661
0x180006671  xor     edi, edi
0x180006673  mov     [rsp+38h+var_18], rdi
0x180006678  jmp     short loc_180006656
0x18000667a  jmp     short loc_180006686
0x18000667c  mov     rdi, [rsp+38h+var_18]
0x180006681  mov     rsi, [rsp+38h+arg_0]
0x180006686  mov     rcx, [rsi]; lpCriticalSection
0x180006689  call    cs:__imp_LeaveCriticalSection
0x18000668f  mov     rax, rdi
0x180006692  mov     rbx, [rsp+38h+arg_8]
0x180006697  mov     rsi, [rsp+38h+arg_10]
0x18000669c  add     rsp, 30h
0x1800066a0  pop     rdi
0x1800066a1  retn
0x1800066a2  xor     eax, eax
0x1800066a4  mov     rbx, [rsp+38h+arg_8]
0x1800066a9  mov     rsi, [rsp+38h+arg_10]
0x1800066ae  add     rsp, 30h
0x1800066b2  pop     rdi
0x1800066b3  retn
```
