# PpRegStateReadCreateClassCreationSettings

- ea: `0x140021234`
- end: `0x140021398`
- name: `PpRegStateReadCreateClassCreationSettings`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400202a0`

## callees

- `0x140007dc4`
- `0x140020eb8`
- `0x14002104c`
- `0x140021234`
- `0x1400216f0`
- `0x1400218f0`
- `0x140021ad4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400212c0`
- `ntoskrnl!ZwClose` at `0x140021379`
- `ntoskrnl!ZwClose` at `0x1400212c0`
- `ntoskrnl!ZwClose` at `0x140021379`

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
  ULONG v11; // [rsp+60h] [rbp+20h] BYREF
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
0x140021234  mov     [rsp-8+arg_0], rbx
0x140021239  mov     [rsp-8+arg_8], rdi
0x14002123e  push    rbp
0x14002123f  mov     rbp, rsp
0x140021242  sub     rsp, 40h
0x140021246  mov     rdi, r8
0x140021249  mov     qword ptr [r8], 0
0x140021250  mov     qword ptr [r8+8], 0
0x140021258  lea     rax, [rbp+Handle]
0x14002125c  mov     qword ptr [r8+10h], 0
0x140021264  lea     r9, [rbp+arg_10]
0x140021268  mov     r8d, 1
0x14002126e  mov     [rsp+40h+var_20], rax
0x140021273  mov     rbx, rdx
0x140021276  mov     [rbp+arg_10], 0
0x14002127d  mov     [rbp+Handle], 0
0x140021285  mov     qword ptr [rbp+DestinationString.Length], 0
0x14002128d  call    PiRegStateOpenClassKey
0x140021292  test    eax, eax
0x140021294  js      loc_140021387
0x14002129a  cmp     [rbp+arg_10], 2
0x14002129e  jnz     short loc_1400212FA
0x1400212a0  mov     rcx, [rbp+Handle]
0x1400212a4  lea     r9, [rbp+DestinationString]
0x1400212a8  mov     r8d, 20019h
0x1400212ae  lea     rdx, aProperties; "Properties"
0x1400212b5  call    CmRegUtilOpenExistingWstrKey
0x1400212ba  mov     rcx, [rbp+Handle]; Handle
0x1400212be  mov     ebx, eax
0x1400212c0  call    cs:__imp_ZwClose
0x1400212c7  nop     dword ptr [rax+rax+00h]
0x1400212cc  test    ebx, ebx
0x1400212ce  js      short loc_1400212E7
0x1400212d0  mov     rcx, qword ptr [rbp+DestinationString.Length]; KeyHandle
0x1400212d4  mov     rdx, rdi
0x1400212d7  call    PiRegStateReadStackCreationSettingsFromKey
0x1400212dc  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x1400212e0  mov     ebx, eax
0x1400212e2  jmp     loc_140021379
0x1400212e7  cmp     ebx, 0C0000034h
0x1400212ed  jnz     loc_140021385
0x1400212f3  xor     ebx, ebx
0x1400212f5  jmp     loc_140021385
0x1400212fa  mov     r10, [rbx+30h]
0x1400212fe  mov     rdi, [rbp+Handle]
0x140021302  add     r10, 18h
0x140021306  jnz     short loc_14002130F
0x140021308  mov     ebx, 0C000009Ah
0x14002130d  jmp     short loc_140021376
0x14002130f  xorps   xmm0, xmm0
0x140021312  lea     rdx, aClass; "Class"
0x140021319  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002131d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140021321  call    WdmlibRtlInitUnicodeStringEx
0x140021326  mov     ebx, eax
0x140021328  test    eax, eax
0x14002132a  js      short loc_140021376
0x14002132c  mov     r8, r10
0x14002132f  lea     rdx, [rbp+DestinationString]; ValueName
0x140021333  mov     rcx, rdi; KeyHandle
0x140021336  call    CmRegUtilUcValueSetUcString
0x14002133b  mov     ebx, eax
0x14002133d  test    eax, eax
0x14002133f  js      short loc_140021376
0x140021341  lea     r8, [rbp+arg_10]
0x140021345  mov     [rbp+arg_10], 31h ; '1'
0x14002134c  lea     rdx, aNodisplayclass; "NoDisplayClass"
0x140021353  mov     rcx, rdi
0x140021356  call    CmRegUtilWstrValueSetWstrString
0x14002135b  mov     ebx, eax
0x14002135d  test    eax, eax
0x14002135f  js      short loc_140021376
0x140021361  lea     r8, [rbp+arg_10]
0x140021365  mov     rcx, rdi
0x140021368  lea     rdx, aNouseclass; "NoUseClass"
0x14002136f  call    CmRegUtilWstrValueSetWstrString
0x140021374  mov     ebx, eax
0x140021376  mov     rcx, rdi; Handle
0x140021379  call    cs:__imp_ZwClose
0x140021380  nop     dword ptr [rax+rax+00h]
0x140021385  mov     eax, ebx
0x140021387  mov     rbx, [rsp+40h+arg_0]
0x14002138c  mov     rdi, [rsp+40h+arg_8]
0x140021391  add     rsp, 40h
0x140021395  pop     rbp
0x140021396  retn
```
