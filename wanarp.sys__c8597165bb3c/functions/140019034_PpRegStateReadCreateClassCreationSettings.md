# PpRegStateReadCreateClassCreationSettings

- ea: `0x140019034`
- end: `0x140019198`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400180b0`

## callees

- `0x140004f04`
- `0x140018cb8`
- `0x140018e4c`
- `0x140019034`
- `0x140019528`
- `0x140019728`
- `0x14001990c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400190c0`
- `ntoskrnl!ZwClose` at `0x140019179`
- `ntoskrnl!ZwClose` at `0x1400190c0`
- `ntoskrnl!ZwClose` at `0x140019179`

## pseudocode

```c
NTSTATUS __fastcall PpRegStateReadCreateClassCreationSettings(unsigned int *a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS result; // eax
  NTSTATUS inited; // ebx
  NTSTATUS StackCreationSettingsFromKey; // eax
  void *v8; // rcx
  HANDLE v9; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+60h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+28h] BYREF

  *a3 = 0;
  a3[1] = 0;
  a3[2] = 0;
  v11 = 0;
  Handle = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  result = PiRegStateOpenClassKey(a1, a2, 1, &v11, &Handle);
  if ( result >= 0 )
  {
    if ( v11 == 2 )
    {
      inited = CmRegUtilOpenExistingWstrKey((__int64)Handle, L"Properties", 131097, (void **)&DestinationString);
      ZwClose(Handle);
      if ( inited < 0 )
      {
        if ( inited == -1073741772 )
          return 0;
        return inited;
      }
      StackCreationSettingsFromKey = PiRegStateReadStackCreationSettingsFromKey(
                                       *(HANDLE *)&DestinationString.Length,
                                       (__int64)a3);
      v8 = *(void **)&DestinationString.Length;
      inited = StackCreationSettingsFromKey;
    }
    else
    {
      v9 = Handle;
      if ( *(_QWORD *)(a2 + 48) == -24 )
      {
        inited = -1073741670;
      }
      else
      {
        DestinationString = 0;
        inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Class");
        if ( inited >= 0 )
        {
          inited = CmRegUtilUcValueSetUcString(v9, &DestinationString);
          if ( inited >= 0 )
          {
            v11 = 49;
            inited = CmRegUtilWstrValueSetWstrString(v9, L"NoDisplayClass", &v11);
            if ( inited >= 0 )
              inited = CmRegUtilWstrValueSetWstrString(v9, L"NoUseClass", &v11);
          }
        }
      }
      v8 = v9;
    }
    ZwClose(v8);
    return inited;
  }
  return result;
}

```

## disassembly

```asm
0x140019034  mov     [rsp-8+arg_0], rbx
0x140019039  mov     [rsp-8+arg_8], rdi
0x14001903e  push    rbp
0x14001903f  mov     rbp, rsp
0x140019042  sub     rsp, 40h
0x140019046  mov     rdi, r8
0x140019049  mov     qword ptr [r8], 0
0x140019050  mov     qword ptr [r8+8], 0
0x140019058  lea     rax, [rbp+Handle]
0x14001905c  mov     qword ptr [r8+10h], 0
0x140019064  lea     r9, [rbp+arg_10]
0x140019068  mov     r8d, 1
0x14001906e  mov     [rsp+40h+var_20], rax
0x140019073  mov     rbx, rdx
0x140019076  mov     [rbp+arg_10], 0
0x14001907d  mov     [rbp+Handle], 0
0x140019085  mov     qword ptr [rbp+DestinationString.Length], 0
0x14001908d  call    PiRegStateOpenClassKey
0x140019092  test    eax, eax
0x140019094  js      loc_140019187
0x14001909a  cmp     [rbp+arg_10], 2
0x14001909e  jnz     short loc_1400190FA
0x1400190a0  mov     rcx, [rbp+Handle]
0x1400190a4  lea     r9, [rbp+DestinationString]
0x1400190a8  mov     r8d, 20019h
0x1400190ae  lea     rdx, aProperties; "Properties"
0x1400190b5  call    CmRegUtilOpenExistingWstrKey
0x1400190ba  mov     rcx, [rbp+Handle]; Handle
0x1400190be  mov     ebx, eax
0x1400190c0  call    cs:__imp_ZwClose
0x1400190c7  nop     dword ptr [rax+rax+00h]
0x1400190cc  test    ebx, ebx
0x1400190ce  js      short loc_1400190E7
0x1400190d0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x1400190d4  mov     rdx, rdi
0x1400190d7  call    PiRegStateReadStackCreationSettingsFromKey
0x1400190dc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x1400190e0  mov     ebx, eax
0x1400190e2  jmp     loc_140019179
0x1400190e7  cmp     ebx, 0C0000034h
0x1400190ed  jnz     loc_140019185
0x1400190f3  xor     ebx, ebx
0x1400190f5  jmp     loc_140019185
0x1400190fa  mov     r10, [rbx+30h]
0x1400190fe  mov     rdi, [rbp+Handle]
0x140019102  add     r10, 18h
0x140019106  jnz     short loc_14001910F
0x140019108  mov     ebx, 0C000009Ah
0x14001910d  jmp     short loc_140019176
0x14001910f  xorps   xmm0, xmm0
0x140019112  lea     rdx, aClass; "Class"
0x140019119  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001911d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140019121  call    WdmlibRtlInitUnicodeStringEx
0x140019126  mov     ebx, eax
0x140019128  test    eax, eax
0x14001912a  js      short loc_140019176
0x14001912c  mov     r8, r10
0x14001912f  lea     rdx, [rbp+DestinationString]; ValueName
0x140019133  mov     rcx, rdi; KeyHandle
0x140019136  call    CmRegUtilUcValueSetUcString
0x14001913b  mov     ebx, eax
0x14001913d  test    eax, eax
0x14001913f  js      short loc_140019176
0x140019141  lea     r8, [rbp+arg_10]
0x140019145  mov     [rbp+arg_10], 31h ; '1'
0x14001914c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140019153  mov     rcx, rdi
0x140019156  call    CmRegUtilWstrValueSetWstrString
0x14001915b  mov     ebx, eax
0x14001915d  test    eax, eax
0x14001915f  js      short loc_140019176
0x140019161  lea     r8, [rbp+arg_10]
0x140019165  mov     rcx, rdi
0x140019168  lea     rdx, aNouseclass; "NoUseClass"
0x14001916f  call    CmRegUtilWstrValueSetWstrString
0x140019174  mov     ebx, eax
0x140019176  mov     rcx, rdi; Handle
0x140019179  call    cs:__imp_ZwClose
0x140019180  nop     dword ptr [rax+rax+00h]
0x140019185  mov     eax, ebx
0x140019187  mov     rbx, [rsp+40h+arg_0]
0x14001918c  mov     rdi, [rsp+40h+arg_8]
0x140019191  add     rsp, 40h
0x140019195  pop     rbp
0x140019196  retn
```
