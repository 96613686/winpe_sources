# RtlUnicodeStringCopy

- ea: `0x1400107d0`
- end: `0x14001087e`
- name: `RtlUnicodeStringCopy`
- size: `174`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140013618`
- `0x140013a68`
- `0x140013fd4`
- `0x140014984`
- `0x140014b34`
- `0x140024b80`

## callees

- `0x1400107d0`
- `0x140010884`

## pseudocode

```c
NTSTATUS __stdcall RtlUnicodeStringCopy(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)
{
  ULONG v2; // r8d
  size_t v5; // rdx
  __int64 v6; // rcx
  ULONG v7; // r8d
  int v8; // r10d
  _WORD *v9; // rsi
  __int64 v10; // r11
  wchar_t *Buffer; // r8
  unsigned __int64 v12; // rdx
  __int16 v13; // cx

  v8 = RtlUnicodeStringValidateWorker(DestinationString, (const size_t)SourceString, v2);
  if ( v8 >= 0 )
  {
    v9 = 0;
    if ( v6 )
      v9 = *(_WORD **)(v6 + 8);
    v8 = RtlUnicodeStringValidateWorker(SourceString, v5, v7);
    if ( v8 < 0 )
    {
      v13 = 0;
    }
    else
    {
      Buffer = 0;
      v12 = 0;
      if ( SourceString )
      {
        Buffer = SourceString->Buffer;
        v12 = (unsigned __int64)SourceString->Length >> 1;
      }
      v8 = 0;
      v13 = 0;
      if ( v10 )
      {
        while ( v12 )
        {
          --v12;
          *v9++ = *Buffer++;
          ++v13;
          if ( !--v10 )
            goto LABEL_10;
        }
      }
      else
      {
LABEL_10:
        if ( v12 )
          v8 = -2147483643;
      }
    }
    DestinationString->Length = 2 * v13;
  }
  return v8;
}

```

## disassembly

```asm
0x1400107d0  mov     [rsp+arg_0], rbx
0x1400107d5  mov     [rsp+arg_8], rsi
0x1400107da  push    rdi
0x1400107db  sub     rsp, 20h
0x1400107df  mov     rdi, rdx
0x1400107e2  mov     rbx, rcx
0x1400107e5  call    RtlUnicodeStringValidateWorker
0x1400107ea  mov     r10d, eax
0x1400107ed  test    eax, eax
0x1400107ef  js      short loc_14001086A
0x1400107f1  xor     esi, esi
0x1400107f3  xor     r11d, r11d
0x1400107f6  test    rcx, rcx
0x1400107f9  jz      short loc_140010807
0x1400107fb  movzx   r11d, word ptr [rcx+2]
0x140010800  mov     rsi, [rcx+8]
0x140010804  shr     r11, 1
0x140010807  mov     rcx, rdi; SourceString
0x14001080a  call    RtlUnicodeStringValidateWorker
0x14001080f  mov     r10d, eax
0x140010812  test    eax, eax
0x140010814  js      short loc_140010862
0x140010816  xor     r8d, r8d
0x140010819  xor     edx, edx
0x14001081b  test    rdi, rdi
0x14001081e  jz      short loc_14001082A
0x140010820  movzx   edx, word ptr [rdi]
0x140010823  mov     r8, [rdi+8]
0x140010827  shr     rdx, 1
0x14001082a  xor     r10d, r10d
0x14001082d  xor     ecx, ecx
0x14001082f  test    r11, r11
0x140010832  jz      short loc_140010854
0x140010834  test    rdx, rdx
0x140010837  jz      short loc_140010864
0x140010839  movzx   eax, word ptr [r8]
0x14001083d  dec     rdx
0x140010840  mov     [rsi], ax
0x140010843  add     r8, 2
0x140010847  add     rsi, 2
0x14001084b  inc     rcx
0x14001084e  sub     r11, 1
0x140010852  jnz     short loc_140010834
0x140010854  test    rdx, rdx
0x140010857  mov     eax, 80000005h
0x14001085c  cmovnz  r10d, eax
0x140010860  jmp     short loc_140010864
0x140010862  xor     ecx, ecx
0x140010864  add     cx, cx
0x140010867  mov     [rbx], cx
0x14001086a  mov     rbx, [rsp+28h+arg_0]
0x14001086f  mov     eax, r10d
0x140010872  mov     rsi, [rsp+28h+arg_8]
0x140010877  add     rsp, 20h
0x14001087b  pop     rdi
0x14001087c  retn
```
