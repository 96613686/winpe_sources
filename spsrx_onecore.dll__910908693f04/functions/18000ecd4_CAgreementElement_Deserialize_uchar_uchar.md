# CAgreementElement::Deserialize(uchar * &,uchar *)

- ea: `0x18000ecd4`
- end: `0x18000ed97`
- name: `?Deserialize@CAgreementElement@@QEAAJAEAPEAEPEAE@Z`
- size: `195`
- prototype: `__int64 __fastcall(CAgreementElement *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b208`

## callees

- `0x180008f2c`
- `0x180008fa4`
- `0x18000ec18`
- `0x18000ecd4`

## pseudocode

```c
__int64 __fastcall CAgreementElement::Deserialize(CAgreementElement *this, unsigned __int8 **a2, unsigned __int8 *a3)
{
  int v6; // ebx
  int i; // edi
  unsigned __int16 v9; // [rsp+40h] [rbp+8h] BYREF
  int v10; // [rsp+58h] [rbp+20h] BYREF

  v6 = SafeMemCopyAndAdvanceInput<long>(this, (const void *const *)a2, a3);
  if ( v6 >= 0 )
  {
    v6 = SafeMemCopyAndAdvanceInput<unsigned short>((char *)this + 4, (const void *const *)a2, a3, 1);
    if ( v6 >= 0 )
    {
      v10 = 0;
      v6 = SafeMemCopyAndAdvanceInput<long>(&v10, (const void *const *)a2, a3);
      if ( v6 >= 0 )
      {
        for ( i = 0; i < v10; ++i )
        {
          v9 = 0;
          v6 = SafeMemCopyAndAdvanceInput<unsigned short>(&v9, (const void *const *)a2, a3, 1);
          if ( v6 < 0 )
            break;
          if ( !CSPList<unsigned short,unsigned short>::AddTail((char *)this + 8, v9) )
            return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ecd4  mov     [rsp+arg_8], rbx
0x18000ecd9  mov     [rsp+arg_10], rbp
0x18000ecde  push    rsi
0x18000ecdf  push    rdi
0x18000ece0  push    r15
0x18000ece2  sub     rsp, 20h
0x18000ece6  mov     rsi, r8
0x18000ece9  mov     rbp, rdx
0x18000ecec  mov     r15, rcx
0x18000ecef  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000ecf4  mov     ebx, eax
0x18000ecf6  test    eax, eax
0x18000ecf8  js      loc_18000ED82
0x18000ecfe  lea     rcx, [r15+4]
0x18000ed02  mov     r9d, 1
0x18000ed08  mov     r8, rsi
0x18000ed0b  mov     rdx, rbp
0x18000ed0e  call    ??$SafeMemCopyAndAdvanceInput@G@@YAJPEAGAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<ushort>(ushort *,uchar * &,uchar *,long)
0x18000ed13  mov     ebx, eax
0x18000ed15  test    eax, eax
0x18000ed17  js      short loc_18000ED82
0x18000ed19  mov     r8, rsi
0x18000ed1c  mov     [rsp+38h+arg_18], 0
0x18000ed24  mov     rdx, rbp
0x18000ed27  lea     rcx, [rsp+38h+arg_18]
0x18000ed2c  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000ed31  mov     ebx, eax
0x18000ed33  test    eax, eax
0x18000ed35  js      short loc_18000ED82
0x18000ed37  xor     edi, edi
0x18000ed39  cmp     [rsp+38h+arg_18], edi
0x18000ed3d  jle     short loc_18000ED82
0x18000ed3f  xor     eax, eax
0x18000ed41  lea     rcx, [rsp+38h+arg_0]
0x18000ed46  mov     r8, rsi
0x18000ed49  mov     [rsp+38h+arg_0], ax
0x18000ed4e  mov     rdx, rbp
0x18000ed51  lea     r9d, [rax+1]
0x18000ed55  call    ??$SafeMemCopyAndAdvanceInput@G@@YAJPEAGAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<ushort>(ushort *,uchar * &,uchar *,long)
0x18000ed5a  mov     ebx, eax
0x18000ed5c  test    eax, eax
0x18000ed5e  js      short loc_18000ED82
0x18000ed60  movzx   edx, [rsp+38h+arg_0]
0x18000ed65  lea     rcx, [r15+8]
0x18000ed69  call    ?AddTail@?$CSPList@GG@@QEAAPEAXG@Z; CSPList<ushort,ushort>::AddTail(ushort)
0x18000ed6e  test    rax, rax
0x18000ed71  jz      short loc_18000ED7D
0x18000ed73  inc     edi
0x18000ed75  cmp     edi, [rsp+38h+arg_18]
0x18000ed79  jl      short loc_18000ED3F
0x18000ed7b  jmp     short loc_18000ED82
0x18000ed7d  mov     ebx, 8007000Eh
0x18000ed82  mov     rbp, [rsp+38h+arg_10]
0x18000ed87  mov     eax, ebx
0x18000ed89  mov     rbx, [rsp+38h+arg_8]
0x18000ed8e  add     rsp, 20h
0x18000ed92  pop     r15
0x18000ed94  pop     rdi
0x18000ed95  pop     rsi
0x18000ed96  retn
```
