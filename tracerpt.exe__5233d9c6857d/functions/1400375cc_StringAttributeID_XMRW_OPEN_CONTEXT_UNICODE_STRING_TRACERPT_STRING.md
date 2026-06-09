# StringAttributeID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_STRING *)

- ea: `0x1400375cc`
- end: `0x14003768f`
- name: `?StringAttributeID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_STRING@@@Z`
- size: `195`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140037698`

## callees

- `0x140030910`
- `0x140035a14`
- `0x1400365a8`
- `0x14003694c`
- `0x1400375cc`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall StringAttributeID(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_STRING *a3)
{
  bool v3; // zf
  __int64 v5; // rsi
  char v6; // al
  __int64 result; // rax
  char *v8; // rbx
  unsigned int v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+20h] BYREF

  v3 = *((_BYTE *)a1 + 144) == 0;
  v5 = *((_QWORD *)a1 + 8);
  v10 = 0;
  v9 = 0;
  if ( !v3 || v5 )
  {
    v6 = *((_BYTE *)a3 + 96);
    if ( (v6 & 1) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v9);
      PrintMessage(0x45Eu, v9);
      return 3221745153LL;
    }
    v8 = (char *)a3 + 16;
    *((_BYTE *)a3 + 96) = v6 | 1;
    *((_BYTE *)a3 + 48) = 0;
    RPT_STRING::operator=((char *)a3 + 16, a2);
    if ( !*((_BYTE *)a1 + 144) )
    {
      result = HashTable<RPT_STRING,0,0>::Find(v5 + 104, v8 + 8, &v10);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result != 1168 )
          return result;
        HashTable<RPT_STRING,0,0>::Insert(v5 + 104, v8);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400375cc  mov     rax, rsp
0x1400375cf  mov     [rax+10h], rbx
0x1400375d3  mov     [rax+18h], rsi
0x1400375d7  push    rdi
0x1400375d8  sub     rsp, 20h
0x1400375dc  cmp     byte ptr [rcx+90h], 0
0x1400375e3  mov     rdi, rcx
0x1400375e6  mov     rsi, [rcx+40h]
0x1400375ea  mov     qword ptr [rax+20h], 0
0x1400375f2  mov     dword ptr [rax+8], 0
0x1400375f9  jnz     short loc_140037600
0x1400375fb  test    rsi, rsi
0x1400375fe  jz      short loc_14003767D
0x140037600  mov     al, [r8+60h]
0x140037604  test    al, 1
0x140037606  jz      short loc_140037635
0x140037608  mov     rcx, [rcx+18h]
0x14003760c  lea     rdx, [rsp+28h+arg_0]
0x140037611  mov     rax, [rcx]
0x140037614  mov     rax, [rax+0A8h]
0x14003761b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037620  mov     edx, [rsp+28h+arg_0]
0x140037624  mov     ecx, 45Eh; unsigned int
0x140037629  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003762e  mov     eax, 0C007EE01h
0x140037633  jmp     short loc_14003767F
0x140037635  lea     rbx, [r8+10h]
0x140037639  or      al, 1
0x14003763b  mov     rcx, rbx
0x14003763e  mov     [r8+60h], al
0x140037642  mov     byte ptr [rbx+20h], 0
0x140037646  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x14003764b  cmp     byte ptr [rdi+90h], 0
0x140037652  jnz     short loc_14003767D
0x140037654  lea     rdx, [rbx+8]
0x140037658  lea     r8, [rsp+28h+arg_18]
0x14003765d  lea     rcx, [rsi+68h]
0x140037661  call    ?Find@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAU_UNICODE_STRING@@PEAPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Find(_UNICODE_STRING *,RPT_STRING * *)
0x140037666  test    eax, eax
0x140037668  jz      short loc_14003767D
0x14003766a  cmp     eax, 490h
0x14003766f  jnz     short loc_14003767F
0x140037671  mov     rdx, rbx
0x140037674  lea     rcx, [rsi+68h]
0x140037678  call    ?Insert@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Insert(RPT_STRING *)
0x14003767d  xor     eax, eax
0x14003767f  mov     rbx, [rsp+28h+arg_8]
0x140037684  mov     rsi, [rsp+28h+arg_10]
0x140037689  add     rsp, 20h
0x14003768d  pop     rdi
0x14003768e  retn
```
