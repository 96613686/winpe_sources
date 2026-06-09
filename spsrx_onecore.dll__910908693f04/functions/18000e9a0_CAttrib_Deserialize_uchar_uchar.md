# CAttrib::Deserialize(uchar * &,uchar *)

- ea: `0x18000e9a0`
- end: `0x18000ea12`
- name: `?Deserialize@CAttrib@@QEAAJAEAPEAEPEAE@Z`
- size: `114`
- prototype: `__int64 __fastcall(CAttrib *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ea18`

## callees

- `0x180008f2c`
- `0x180008fa4`
- `0x18000e760`
- `0x18000e9a0`

## pseudocode

```c
int __fastcall CAttrib::Deserialize(CAttrib *this, unsigned __int8 **a2, unsigned __int8 *a3)
{
  int result; // eax

  result = SafeMemCopyAndAdvanceInput<unsigned short>(this, (const void *const *)a2, a3, 1);
  if ( result >= 0 )
  {
    result = SafeMemCopyAndAdvanceInput<unsigned short>((char *)this + 2, (const void *const *)a2, a3, 1);
    if ( result >= 0 )
    {
      result = SafeMemCopyAndAdvanceInput<long>((char *)this + 4, (const void *const *)a2, a3);
      if ( result >= 0 )
        return SafeMemCopyAndAdvanceInput<bool>((char *)this + 8, a2, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e9a0  mov     [rsp+arg_0], rbx
0x18000e9a5  mov     [rsp+arg_8], rsi
0x18000e9aa  push    rdi
0x18000e9ab  sub     rsp, 20h
0x18000e9af  mov     r9d, 1
0x18000e9b5  mov     rbx, r8
0x18000e9b8  mov     rdi, rdx
0x18000e9bb  mov     rsi, rcx
0x18000e9be  call    ??$SafeMemCopyAndAdvanceInput@G@@YAJPEAGAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<ushort>(ushort *,uchar * &,uchar *,long)
0x18000e9c3  test    eax, eax
0x18000e9c5  js      short loc_18000EA02
0x18000e9c7  lea     rcx, [rsi+2]
0x18000e9cb  mov     r9d, 1
0x18000e9d1  mov     r8, rbx
0x18000e9d4  mov     rdx, rdi
0x18000e9d7  call    ??$SafeMemCopyAndAdvanceInput@G@@YAJPEAGAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<ushort>(ushort *,uchar * &,uchar *,long)
0x18000e9dc  test    eax, eax
0x18000e9de  js      short loc_18000EA02
0x18000e9e0  lea     rcx, [rsi+4]
0x18000e9e4  mov     r8, rbx
0x18000e9e7  mov     rdx, rdi
0x18000e9ea  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000e9ef  test    eax, eax
0x18000e9f1  js      short loc_18000EA02
0x18000e9f3  lea     rcx, [rsi+8]
0x18000e9f7  mov     r8, rbx
0x18000e9fa  mov     rdx, rdi
0x18000e9fd  call    ??$SafeMemCopyAndAdvanceInput@_N@@YAJPEA_NAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<bool>(bool *,uchar * &,uchar *,long)
0x18000ea02  mov     rbx, [rsp+28h+arg_0]
0x18000ea07  mov     rsi, [rsp+28h+arg_8]
0x18000ea0c  add     rsp, 20h
0x18000ea10  pop     rdi
0x18000ea11  retn
```
