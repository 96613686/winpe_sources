# PpRegStateReadCreateClassCreationSettings

- ea: `0x140021df4`
- end: `0x140021f58`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140020e70`

## callees

- `0x1400120a8`
- `0x140021a78`
- `0x140021c0c`
- `0x140021df4`
- `0x1400222e8`
- `0x1400224e8`
- `0x1400226cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140021e80`
- `ntoskrnl!ZwClose` at `0x140021f39`
- `ntoskrnl!ZwClose` at `0x140021e80`
- `ntoskrnl!ZwClose` at `0x140021f39`

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
0x140021df4  mov     [rsp-8+arg_0], rbx
0x140021df9  mov     [rsp-8+arg_8], rdi
0x140021dfe  push    rbp
0x140021dff  mov     rbp, rsp
0x140021e02  sub     rsp, 40h
0x140021e06  mov     rdi, r8
0x140021e09  mov     qword ptr [r8], 0
0x140021e10  mov     qword ptr [r8+8], 0
0x140021e18  lea     rax, [rbp+Handle]
0x140021e1c  mov     qword ptr [r8+10h], 0
0x140021e24  lea     r9, [rbp+arg_10]
0x140021e28  mov     r8d, 1
0x140021e2e  mov     [rsp+40h+var_20], rax
0x140021e33  mov     rbx, rdx
0x140021e36  mov     [rbp+arg_10], 0
0x140021e3d  mov     [rbp+Handle], 0
0x140021e45  mov     qword ptr [rbp+DestinationString.Length], 0
0x140021e4d  call    PiRegStateOpenClassKey
0x140021e52  test    eax, eax
0x140021e54  js      loc_140021F47
0x140021e5a  cmp     [rbp+arg_10], 2
0x140021e5e  jnz     short loc_140021EBA
0x140021e60  mov     rcx, [rbp+Handle]
0x140021e64  lea     r9, [rbp+DestinationString]
0x140021e68  mov     r8d, 20019h
0x140021e6e  lea     rdx, aProperties; "Properties"
0x140021e75  call    CmRegUtilOpenExistingWstrKey
0x140021e7a  mov     rcx, [rbp+Handle]; Handle
0x140021e7e  mov     ebx, eax
0x140021e80  call    cs:__imp_ZwClose
0x140021e87  nop     dword ptr [rax+rax+00h]
0x140021e8c  test    ebx, ebx
0x140021e8e  js      short loc_140021EA7
0x140021e90  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x140021e94  mov     rdx, rdi
0x140021e97  call    PiRegStateReadStackCreationSettingsFromKey
0x140021e9c  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x140021ea0  mov     ebx, eax
0x140021ea2  jmp     loc_140021F39
0x140021ea7  cmp     ebx, 0C0000034h
0x140021ead  jnz     loc_140021F45
0x140021eb3  xor     ebx, ebx
0x140021eb5  jmp     loc_140021F45
0x140021eba  mov     r10, [rbx+30h]
0x140021ebe  mov     rdi, [rbp+Handle]
0x140021ec2  add     r10, 18h
0x140021ec6  jnz     short loc_140021ECF
0x140021ec8  mov     ebx, 0C000009Ah
0x140021ecd  jmp     short loc_140021F36
0x140021ecf  xorps   xmm0, xmm0
0x140021ed2  lea     rdx, aClass; "Class"
0x140021ed9  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021edd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140021ee1  call    WdmlibRtlInitUnicodeStringEx
0x140021ee6  mov     ebx, eax
0x140021ee8  test    eax, eax
0x140021eea  js      short loc_140021F36
0x140021eec  mov     r8, r10
0x140021eef  lea     rdx, [rbp+DestinationString]; ValueName
0x140021ef3  mov     rcx, rdi; KeyHandle
0x140021ef6  call    CmRegUtilUcValueSetUcString
0x140021efb  mov     ebx, eax
0x140021efd  test    eax, eax
0x140021eff  js      short loc_140021F36
0x140021f01  lea     r8, [rbp+arg_10]
0x140021f05  mov     [rbp+arg_10], 31h ; '1'
0x140021f0c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140021f13  mov     rcx, rdi
0x140021f16  call    CmRegUtilWstrValueSetWstrString
0x140021f1b  mov     ebx, eax
0x140021f1d  test    eax, eax
0x140021f1f  js      short loc_140021F36
0x140021f21  lea     r8, [rbp+arg_10]
0x140021f25  mov     rcx, rdi
0x140021f28  lea     rdx, aNouseclass; "NoUseClass"
0x140021f2f  call    CmRegUtilWstrValueSetWstrString
0x140021f34  mov     ebx, eax
0x140021f36  mov     rcx, rdi; Handle
0x140021f39  call    cs:__imp_ZwClose
0x140021f40  nop     dword ptr [rax+rax+00h]
0x140021f45  mov     eax, ebx
0x140021f47  mov     rbx, [rsp+40h+arg_0]
0x140021f4c  mov     rdi, [rsp+40h+arg_8]
0x140021f51  add     rsp, 40h
0x140021f55  pop     rbp
0x140021f56  retn
```
