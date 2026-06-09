# CUsbDevice::GetDescriptorValidationInfo(ulong)

- ea: `0x180008f48`
- end: `0x18000904d`
- name: `?GetDescriptorValidationInfo@CUsbDevice@@QEAAKK@Z`
- size: `261`
- prototype: `__int64 __fastcall(CUsbDevice *this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800045d0`

## callees

- `0x180007248`
- `0x180008f48`
- `0x18000aa38`
- `0x18000bc7c`
- `0x18000bd24`
- `0x18000c088`
- `0x18000c114`

## string_xrefs

- `0x180008fce`: `DescriptorValidationInfo6`
- `0x180008fd7`: `DescriptorValidationInfo5`
- `0x180008fe0`: `DescriptorValidationInfo4`
- `0x180008fe9`: `DescriptorValidationInfo3`
- `0x180008ff2`: `DescriptorValidationInfo2`
- `0x180008ffb`: `DescriptorValidationInfo1`
- `0x180009004`: `DescriptorValidationInfo0`

## pseudocode

```c
__int64 __fastcall CUsbDevice::GetDescriptorValidationInfo(CUsbDevice *this, int a2)
{
  HKEY *v3; // rbx
  int v4; // edi
  int v5; // edi
  int v6; // edi
  int v7; // edi
  int v8; // edi
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // ebx
  HKEY phkResult[4]; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+50h] [rbp+10h] BYREF
  HKEY *v14; // [rsp+60h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  CDevNode::GetHardwareKey(*(_QWORD **)this, (CRegistryKey **)&v14);
  v3 = v14;
  if ( CRegistryKey::KeyExists(*v14, L"Ceip") )
  {
    CRegistryKey::CRegistryKey(phkResult, *v3, L"Ceip");
    if ( a2 )
    {
      v4 = a2 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( v7 )
            {
              v8 = v7 - 1;
              if ( v8 )
              {
                if ( v8 != 1 )
                {
LABEL_17:
                  CRegistryKey::~CRegistryKey((CRegistryKey *)phkResult);
                  goto LABEL_18;
                }
                v9 = L"DescriptorValidationInfo6";
              }
              else
              {
                v9 = L"DescriptorValidationInfo5";
              }
            }
            else
            {
              v9 = L"DescriptorValidationInfo4";
            }
          }
          else
          {
            v9 = L"DescriptorValidationInfo3";
          }
        }
        else
        {
          v9 = L"DescriptorValidationInfo2";
        }
      }
      else
      {
        v9 = L"DescriptorValidationInfo1";
      }
    }
    else
    {
      v9 = L"DescriptorValidationInfo0";
    }
    v13 = 0;
    CRegistryKey::QueryFixedLengthValue((CRegistryKey *)phkResult, v9, 4u, (unsigned __int8 *)&v13);
    goto LABEL_17;
  }
LABEL_18:
  v10 = v13;
  std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(&v14);
  return v10;
}

```

## disassembly

```asm
0x180008f48  mov     [rsp-8+arg_8], rbx
0x180008f4d  mov     [rsp-8+arg_18], rdi
0x180008f52  push    rbp
0x180008f53  mov     rbp, rsp
0x180008f56  sub     rsp, 40h
0x180008f5a  mov     edi, edx
0x180008f5c  mov     [rbp+arg_10], 0
0x180008f64  mov     [rbp+arg_0], 0
0x180008f6b  lea     rdx, [rbp+arg_10]
0x180008f6f  mov     rcx, [rcx]
0x180008f72  call    ?GetHardwareKey@CDevNode@@QEAAXAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z; CDevNode::GetHardwareKey(std::unique_ptr<CRegistryKey> &)
0x180008f77  lea     rdx, aCeip; "Ceip"
0x180008f7e  mov     rbx, [rbp+arg_10]
0x180008f82  mov     rcx, [rbx]; HKEY
0x180008f85  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180008f8a  test    al, al
0x180008f8c  jz      loc_18000902F
0x180008f92  mov     r9d, 1; unsigned int
0x180008f98  lea     r8, aCeip; "Ceip"
0x180008f9f  mov     rdx, [rbx]; HKEY
0x180008fa2  lea     rcx, [rbp+phkResult]; phkResult
0x180008fa6  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180008fab  nop
0x180008fac  test    edi, edi
0x180008fae  jz      short loc_180009004
0x180008fb0  sub     edi, 1
0x180008fb3  jz      short loc_180008FFB
0x180008fb5  sub     edi, 1
0x180008fb8  jz      short loc_180008FF2
0x180008fba  sub     edi, 1
0x180008fbd  jz      short loc_180008FE9
0x180008fbf  sub     edi, 1
0x180008fc2  jz      short loc_180008FE0
0x180008fc4  sub     edi, 1
0x180008fc7  jz      short loc_180008FD7
0x180008fc9  cmp     edi, 1
0x180008fcc  jnz     short loc_180009026
0x180008fce  lea     rdx, aDescriptorvali_0; "DescriptorValidationInfo6"
0x180008fd5  jmp     short loc_18000900B
0x180008fd7  lea     rdx, aDescriptorvali_3; "DescriptorValidationInfo5"
0x180008fde  jmp     short loc_18000900B
0x180008fe0  lea     rdx, aDescriptorvali_1; "DescriptorValidationInfo4"
0x180008fe7  jmp     short loc_18000900B
0x180008fe9  lea     rdx, aDescriptorvali; "DescriptorValidationInfo3"
0x180008ff0  jmp     short loc_18000900B
0x180008ff2  lea     rdx, aDescriptorvali_4; "DescriptorValidationInfo2"
0x180008ff9  jmp     short loc_18000900B
0x180008ffb  lea     rdx, aDescriptorvali_2; "DescriptorValidationInfo1"
0x180009002  jmp     short loc_18000900B
0x180009004  lea     rdx, aDescriptorvali_5; "DescriptorValidationInfo0"
0x18000900b  mov     [rbp+arg_0], 0
0x180009012  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x180009016  mov     r8d, 4; unsigned int
0x18000901c  lea     rcx, [rbp+phkResult]; this
0x180009020  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x180009025  nop
0x180009026  lea     rcx, [rbp+phkResult]; this
0x18000902a  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x18000902f  mov     ebx, [rbp+arg_0]
0x180009032  lea     rcx, [rbp+arg_10]
0x180009036  call    ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
0x18000903b  mov     eax, ebx
0x18000903d  mov     rbx, [rsp+40h+arg_8]
0x180009042  mov     rdi, [rsp+40h+arg_18]
0x180009047  add     rsp, 40h
0x18000904b  pop     rbp
0x18000904c  retn
```
