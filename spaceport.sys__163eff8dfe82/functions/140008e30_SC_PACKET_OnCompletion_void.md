# SC_PACKET::OnCompletion(void)

- ea: `0x140008e30`
- end: `0x140008f09`
- name: `?OnCompletion@SC_PACKET@@QEAAXXZ`
- size: `217`
- prototype: `void __fastcall(SC_PACKET *__hidden this)`
- caller_count: `16`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400084e0`
- `0x140008960`
- `0x1400089b0`
- `0x140008a00`
- `0x140008bc0`
- `0x140008d50`
- `0x140008f10`
- `0x140012600`
- `0x14001b600`
- `0x14001cb10`
- `0x140025890`
- `0x140025f50`
- `0x14002b310`
- `0x14002b920`
- `0x140039850`
- `0x140054054`

## callees

- `0x140008a00`
- `0x140008e30`
- `0x140008f10`
- `0x140025f50`
- `0x140068150`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140008ecf`
- `ntoskrnl!KeSetEvent` at `0x140008ecf`

## pseudocode

```c
void __fastcall SC_PACKET::OnCompletion(PRKEVENT *this)
{
  int v2; // edi
  unsigned __int8 v3; // bp
  PRKEVENT v4; // rsi
  int v5; // eax

  if ( (*((_DWORD *)this + 19) & 8) != 0 )
  {
    KeSetEvent(this[11], 1, 0);
  }
  else
  {
    v2 = *((_DWORD *)this + 19) & 2;
    if ( this[1] == (PRKEVENT)this )
    {
      v3 = *((_BYTE *)this + 169);
      v4 = this[29];
      v5 = (*(__int64 (__fastcall **)(PRKEVENT, PRKEVENT *))(*(_QWORD *)&v4->Header.Lock + 64LL))(v4, this);
      if ( v5 != -1073741802 )
      {
        if ( v5 == -1073741267 )
        {
          SC_DISPATCH::Dispatch(v4, this, v3);
        }
        else if ( !v2 )
        {
          (*(void (__fastcall **)(PRKEVENT *, __int64))&(*this)->Header.Lock)(this, 1);
        }
      }
    }
    else if ( v2 )
    {
      SC_PACKET::OnCompletionSequential((SC_PACKET *)this);
    }
    else
    {
      SC_PACKET::OnCompletionParallel((SC_PACKET *)this);
    }
  }
}

```

## disassembly

```asm
0x140008e30  mov     [rsp+arg_10], rbx
0x140008e35  push    rdi
0x140008e36  sub     rsp, 20h
0x140008e3a  mov     edi, [rcx+4Ch]
0x140008e3d  mov     rbx, rcx
0x140008e40  test    dil, 8
0x140008e44  jnz     short loc_140008EC3
0x140008e46  and     edi, 2
0x140008e49  cmp     [rcx+8], rcx
0x140008e4d  jz      short loc_140008E68
0x140008e4f  test    edi, edi
0x140008e51  jnz     loc_140008EE7
0x140008e57  call    ?OnCompletionParallel@SC_PACKET@@AEAAXXZ; SC_PACKET::OnCompletionParallel(void)
0x140008e5c  mov     rbx, [rsp+28h+arg_10]
0x140008e61  add     rsp, 20h
0x140008e65  pop     rdi
0x140008e66  retn
0x140008e68  mov     [rsp+28h+arg_0], rbp
0x140008e6d  mov     rdx, rbx
0x140008e70  movzx   ebp, byte ptr [rcx+0A9h]
0x140008e77  mov     [rsp+28h+arg_8], rsi
0x140008e7c  mov     rsi, [rcx+0E8h]
0x140008e83  mov     rcx, rsi
0x140008e86  mov     rax, [rsi]
0x140008e89  mov     rax, [rax+40h]
0x140008e8d  call    _guard_dispatch_icall
0x140008e92  cmp     eax, 0C0000016h
0x140008e97  jz      short loc_140008EB7
0x140008e99  cmp     eax, 0C000022Dh
0x140008e9e  jz      short loc_140008EF8
0x140008ea0  test    edi, edi
0x140008ea2  jnz     short loc_140008EB7
0x140008ea4  mov     rax, [rbx]
0x140008ea7  mov     edx, 1
0x140008eac  mov     rcx, rbx
0x140008eaf  mov     rax, [rax]
0x140008eb2  call    _guard_dispatch_icall
0x140008eb7  mov     rbp, [rsp+28h+arg_0]
0x140008ebc  mov     rsi, [rsp+28h+arg_8]
0x140008ec1  jmp     short loc_140008E5C
0x140008ec3  mov     rcx, [rcx+58h]; Event
0x140008ec7  xor     r8d, r8d; Wait
0x140008eca  mov     edx, 1; Increment
0x140008ecf  call    cs:__imp_KeSetEvent
0x140008ed6  nop     dword ptr [rax+rax+00h]
0x140008edb  mov     rbx, [rsp+28h+arg_10]
0x140008ee0  add     rsp, 20h
0x140008ee4  pop     rdi
0x140008ee5  retn
0x140008ee7  call    ?OnCompletionSequential@SC_PACKET@@AEAAXXZ; SC_PACKET::OnCompletionSequential(void)
0x140008eec  mov     rbx, [rsp+28h+arg_10]
0x140008ef1  add     rsp, 20h
0x140008ef5  pop     rdi
0x140008ef6  retn
0x140008ef8  movzx   r8d, bpl
0x140008efc  mov     rdx, rbx
0x140008eff  mov     rcx, rsi
0x140008f02  call    ?Dispatch@SC_DISPATCH@@QEAAXPEAVSC_PACKET@@W4_SC_OPERATION@@@Z; SC_DISPATCH::Dispatch(SC_PACKET *,_SC_OPERATION)
0x140008f07  jmp     short loc_140008EB7
```
