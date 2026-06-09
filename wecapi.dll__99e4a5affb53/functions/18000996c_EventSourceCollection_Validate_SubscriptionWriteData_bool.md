# EventSourceCollection::Validate(SubscriptionWriteData &,bool)

- ea: `0x18000996c`
- end: `0x180009b99`
- name: `?Validate@EventSourceCollection@@AEBAXAEAVSubscriptionWriteData@@_N@Z`
- size: `557`
- prototype: `void __fastcall(EventSourceCollection *__hidden this, struct SubscriptionWriteData *, bool)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180004b50`
- `0x180005e2c`
- `0x1800064e8`
- `0x180006fb8`
- `0x1800073c4`
- `0x180007720`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x18000996c`

## pseudocode

```c
void __fastcall EventSourceCollection::Validate(EventSourceCollection *this, struct SubscriptionWriteData *a2, char a3)
{
  _DWORD *v3; // rcx
  int v4; // eax
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = *(_DWORD **)(*(_QWORD *)a2 + 8LL);
  if ( v3[12] )
  {
    if ( v3[6] != 7 || v3[12] != 6 || v3[18] != 5 || v3[24] != 6 || v3[30] != 6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 13);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0xDu,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        602);
      throw (wmi::GenericException *)pExceptionObject;
    }
    v4 = v3[14];
    if ( v4 != v3[8] || v4 != v3[20] || v4 != v3[26] || v4 != v3[32] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 13);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0xDu,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        608);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  else
  {
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 13);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0xDu,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        589);
      throw (wmi::GenericException *)pExceptionObject;
    }
    if ( v3[18] || v3[24] || v3[30] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids, 13);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0xDu,
        "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.cpp",
        593);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18000996c  sub     rsp, 68h
0x180009970  mov     rax, [rdx]
0x180009973  mov     rcx, [rax+8]
0x180009977  xor     eax, eax
0x180009979  cmp     [rcx+30h], eax
0x18000997c  jnz     short loc_1800099A0
0x18000997e  test    r8b, r8b
0x180009981  jz      short loc_180009A01
0x180009983  cmp     [rcx+48h], eax
0x180009986  jnz     loc_180009A67
0x18000998c  cmp     [rcx+60h], eax
0x18000998f  jnz     loc_180009A67
0x180009995  cmp     [rcx+78h], eax
0x180009998  jnz     loc_180009A67
0x18000999e  jmp     short loc_1800099FC
0x1800099a0  cmp     dword ptr [rcx+18h], 7
0x1800099a4  jnz     loc_180009B33
0x1800099aa  cmp     dword ptr [rcx+30h], 6
0x1800099ae  jnz     loc_180009B33
0x1800099b4  cmp     dword ptr [rcx+48h], 5
0x1800099b8  jnz     loc_180009B33
0x1800099be  cmp     dword ptr [rcx+60h], 6
0x1800099c2  jnz     loc_180009B33
0x1800099c8  cmp     dword ptr [rcx+78h], 6
0x1800099cc  jnz     loc_180009B33
0x1800099d2  mov     eax, [rcx+38h]
0x1800099d5  cmp     eax, [rcx+20h]
0x1800099d8  jnz     loc_180009ACD
0x1800099de  cmp     eax, [rcx+50h]
0x1800099e1  jnz     loc_180009ACD
0x1800099e7  cmp     eax, [rcx+68h]
0x1800099ea  jnz     loc_180009ACD
0x1800099f0  cmp     eax, [rcx+80h]
0x1800099f6  jnz     loc_180009ACD
0x1800099fc  add     rsp, 68h
0x180009a00  retn
0x180009a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a08  lea     rax, WPP_GLOBAL_Control
0x180009a0f  cmp     rcx, rax
0x180009a12  jz      short loc_180009A39
0x180009a14  test    byte ptr [rcx+1Ch], 1
0x180009a18  jz      short loc_180009A39
0x180009a1a  cmp     byte ptr [rcx+19h], 2
0x180009a1e  jb      short loc_180009A39
0x180009a20  mov     rcx, [rcx+10h]
0x180009a24  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x180009a2b  mov     edx, 43h ; 'C'
0x180009a30  lea     r9d, [rdx-36h]
0x180009a34  call    WPP_SF_D
0x180009a39  mov     r9d, 24Dh; int
0x180009a3f  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x180009a46  mov     edx, 0Dh; unsigned int
0x180009a4b  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180009a50  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180009a55  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009a5c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180009a61  call    _CxxThrowException_0
0x180009a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a6e  lea     rax, WPP_GLOBAL_Control
0x180009a75  cmp     rcx, rax
0x180009a78  jz      short loc_180009A9F
0x180009a7a  test    byte ptr [rcx+1Ch], 1
0x180009a7e  jz      short loc_180009A9F
0x180009a80  cmp     byte ptr [rcx+19h], 2
0x180009a84  jb      short loc_180009A9F
0x180009a86  mov     rcx, [rcx+10h]
0x180009a8a  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x180009a91  mov     edx, 44h ; 'D'
0x180009a96  lea     r9d, [rdx-37h]
0x180009a9a  call    WPP_SF_D
0x180009a9f  mov     r9d, 251h; int
0x180009aa5  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x180009aac  mov     edx, 0Dh; unsigned int
0x180009ab1  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180009ab6  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180009abb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009ac2  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180009ac7  call    _CxxThrowException_0
0x180009acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ad4  lea     rax, WPP_GLOBAL_Control
0x180009adb  cmp     rcx, rax
0x180009ade  jz      short loc_180009B05
0x180009ae0  test    byte ptr [rcx+1Ch], 1
0x180009ae4  jz      short loc_180009B05
0x180009ae6  cmp     byte ptr [rcx+19h], 2
0x180009aea  jb      short loc_180009B05
0x180009aec  mov     rcx, [rcx+10h]
0x180009af0  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x180009af7  mov     edx, 46h ; 'F'
0x180009afc  lea     r9d, [rdx-39h]
0x180009b00  call    WPP_SF_D
0x180009b05  mov     r9d, 260h; int
0x180009b0b  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x180009b12  mov     edx, 0Dh; unsigned int
0x180009b17  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180009b1c  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180009b21  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009b28  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180009b2d  call    _CxxThrowException_0
0x180009b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b3a  lea     rax, WPP_GLOBAL_Control
0x180009b41  cmp     rcx, rax
0x180009b44  jz      short loc_180009B6B
0x180009b46  test    byte ptr [rcx+1Ch], 1
0x180009b4a  jz      short loc_180009B6B
0x180009b4c  cmp     byte ptr [rcx+19h], 2
0x180009b50  jb      short loc_180009B6B
0x180009b52  mov     rcx, [rcx+10h]
0x180009b56  lea     r8, WPP_c9cb5f32fcc639bc5b417ec74ef6cc9f_Traceguids
0x180009b5d  mov     edx, 45h ; 'E'
0x180009b62  lea     r9d, [rdx-38h]
0x180009b66  call    WPP_SF_D
0x180009b6b  mov     r9d, 25Ah; int
0x180009b71  lea     r8, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x180009b78  mov     edx, 0Dh; unsigned int
0x180009b7d  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180009b82  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x180009b87  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180009b8e  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180009b93  call    _CxxThrowException_0
```
