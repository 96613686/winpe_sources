# IsNfcSupported(void)

- ea: `0x180016d20`
- end: `0x18001704e`
- name: `?IsNfcSupported@@YA_NXZ`
- size: `814`
- prototype: `char(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b850`
- `0x180018204`

## callees

- `0x180004fb8`
- `0x180016d20`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `msvcrt!malloc` at `0x180016ec3`
- `msvcrt!malloc` at `0x180016ec3`
- `msvcrt!free` at `0x180016f8e`
- `msvcrt!free` at `0x180017025`
- `msvcrt!free` at `0x180016f8e`
- `msvcrt!free` at `0x180017025`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016f4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016f4b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180016d67`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180016d67`
- `DEVOBJ!DevObjGetClassDevs` at `0x180016dc6`
- `DEVOBJ!DevObjGetClassDevs` at `0x180016dc6`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x180016ea7`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x180016efa`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x180016ea7`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x180016efa`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180016e38`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180016e38`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180016e77`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180016e77`

## pseudocode

```c
char IsNfcSupported(void)
{
  char v0; // r12
  WCHAR *v1; // rsi
  __int64 DeviceInfoList; // rax
  __int64 v3; // r14
  const char *Indent; // rax
  __int64 v5; // r10
  __int64 v6; // rdx
  unsigned __int8 v7; // r15
  int v8; // ebx
  WCHAR *v9; // rax
  const WCHAR *v10; // rbx
  const char *v11; // rax
  __int64 v12; // r10
  const char *v13; // rax
  __int64 v14; // r10
  __int64 v16; // [rsp+28h] [rbp-61h]
  __int64 v17; // [rsp+28h] [rbp-61h]
  size_t Size; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v19[8]; // [rsp+48h] [rbp-41h] BYREF
  int v20; // [rsp+68h] [rbp-21h] BYREF
  __int128 v21; // [rsp+6Ch] [rbp-1Dh]
  _BYTE v22[28]; // [rsp+7Ch] [rbp-Dh] BYREF

  Size = 0;
  v0 = 0;
  v1 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      Indent = GetIndent(0);
      v6 = 184;
LABEL_34:
      WPP_SF_s(*(_QWORD *)(v5 + 16), v6, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    }
  }
  else if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_NFP, 0, 18, 0, 0) )
  {
    v7 = 0;
    while ( 1 )
    {
      v19[0] = 32;
      memset(&v19[1], 0, 28);
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v3, 0, &GUID_DEVINTERFACE_NFP, v7, v19) )
        break;
      v20 = 48;
      memset(v22, 0, sizeof(v22));
      v21 = 0;
      DevObjGetDeviceInterfaceDetail(v3, v19, 0, 0, 0, &v20);
      LODWORD(v16) = 0;
      if ( (unsigned int)DevObjGetDeviceInterfaceProperty(
                           v3,
                           v19,
                           &DEVPKEY_NFP_Capabilities,
                           (char *)&Size + 4,
                           0,
                           v16,
                           &Size,
                           0)
        || (v8 = Size, (unsigned int)Size < 6) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v14 + 16), 188, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v13);
        }
      }
      else
      {
        v9 = (WCHAR *)malloc((unsigned int)Size);
        v1 = v9;
        if ( v9 )
        {
          LODWORD(v17) = v8;
          if ( (unsigned int)DevObjGetDeviceInterfaceProperty(
                               v3,
                               v19,
                               &DEVPKEY_NFP_Capabilities,
                               (char *)&Size + 4,
                               v9,
                               v17,
                               0,
                               0) )
          {
            if ( HIDWORD(Size) == 8210 )
            {
              v10 = v1;
              v1[((unsigned __int64)(unsigned int)Size >> 1) - 1] = 0;
              v1[((unsigned __int64)(unsigned int)Size >> 1) - 2] = 0;
              if ( *v1 )
              {
                while ( CompareStringOrdinal(v10, -1, L"StandardNfc", -1, 1) != 2 )
                {
                  while ( *v10 )
                    ++v10;
                  if ( !*++v10 )
                    goto LABEL_21;
                }
                v0 = 1;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v11 = GetIndent(0);
                  WPP_SF_s(*(_QWORD *)(v12 + 16), 187, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v11);
                }
              }
            }
          }
LABEL_21:
          free(v1);
          v1 = 0;
        }
      }
      if ( ++v7 >= 0xAu )
        goto LABEL_35;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      Indent = GetIndent(0);
      v6 = 186;
      goto LABEL_34;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    Indent = GetIndent(0);
    v6 = 185;
    goto LABEL_34;
  }
LABEL_35:
  free(v1);
  return v0;
}

```

## disassembly

```asm
0x180016d20  push    rbp
0x180016d22  push    rbx
0x180016d23  push    rsi
0x180016d24  push    rdi
0x180016d25  push    r12
0x180016d27  push    r13
0x180016d29  push    r14
0x180016d2b  push    r15
0x180016d2d  lea     rbp, [rsp-1Fh]
0x180016d32  sub     rsp, 0A8h
0x180016d39  mov     rax, cs:__security_cookie
0x180016d40  xor     rax, rsp
0x180016d43  mov     [rbp+57h+var_48], rax
0x180016d47  xor     r13d, r13d
0x180016d4a  xor     r9d, r9d
0x180016d4d  xor     r8d, r8d
0x180016d50  mov     dword ptr [rbp+57h+Size], r13d
0x180016d54  xor     edx, edx
0x180016d56  mov     dword ptr [rbp+57h+Size+4], r13d
0x180016d5a  xor     ecx, ecx
0x180016d5c  mov     qword ptr [rsp+0E0h+bIgnoreCase], r13
0x180016d61  mov     r12b, r13b
0x180016d64  mov     esi, r13d
0x180016d67  call    cs:__imp_DevObjCreateDeviceInfoList
0x180016d6d  mov     r14, rax
0x180016d70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016d74  jnz     short loc_180016DA9
0x180016d76  mov     r10, cs:WPP_GLOBAL_Control
0x180016d7d  lea     rdi, WPP_GLOBAL_Control
0x180016d84  cmp     r10, rdi
0x180016d87  jz      loc_180017022
0x180016d8d  cmp     byte ptr [r10+19h], 2
0x180016d92  jb      loc_180017022
0x180016d98  xor     ecx, ecx; int
0x180016d9a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016d9f  mov     edx, 0B8h
0x180016da4  jmp     loc_18001700F
0x180016da9  mov     [rsp+0E0h+var_B8], r13
0x180016dae  lea     rdx, GUID_DEVINTERFACE_NFP
0x180016db5  mov     r9d, 12h
0x180016dbb  mov     qword ptr [rsp+0E0h+bIgnoreCase], r13
0x180016dc0  xor     r8d, r8d
0x180016dc3  mov     rcx, r14
0x180016dc6  call    cs:__imp_DevObjGetClassDevs
0x180016dcc  test    eax, eax
0x180016dce  jnz     short loc_180016E03
0x180016dd0  mov     r10, cs:WPP_GLOBAL_Control
0x180016dd7  lea     rdi, WPP_GLOBAL_Control
0x180016dde  cmp     r10, rdi
0x180016de1  jz      loc_180017022
0x180016de7  cmp     byte ptr [r10+19h], 2
0x180016dec  jb      loc_180017022
0x180016df2  xor     ecx, ecx; int
0x180016df4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016df9  mov     edx, 0B9h
0x180016dfe  jmp     loc_18001700F
0x180016e03  mov     r15b, r13b
0x180016e06  lea     rdi, WPP_GLOBAL_Control
0x180016e0d  xorps   xmm0, xmm0
0x180016e10  movzx   r9d, r15b
0x180016e14  lea     rax, [rbp+57h+var_98]
0x180016e18  mov     [rbp+57h+var_98], 20h ; ' '
0x180016e1f  movups  xmmword ptr [rbp+57h+var_94], xmm0
0x180016e23  lea     r8, GUID_DEVINTERFACE_NFP
0x180016e2a  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax
0x180016e2f  xor     edx, edx
0x180016e31  mov     rcx, r14
0x180016e34  movups  xmmword ptr [rbp+57h+var_94+0Ch], xmm0
0x180016e38  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180016e3e  test    eax, eax
0x180016e40  jz      loc_180016FF0
0x180016e46  xorps   xmm0, xmm0
0x180016e49  mov     [rbp+57h+var_78], 30h ; '0'
0x180016e50  lea     rax, [rbp+57h+var_78]
0x180016e54  xor     r9d, r9d
0x180016e57  movups  xmmword ptr [rbp+57h+var_64], xmm0
0x180016e5b  mov     [rsp+0E0h+var_B8], rax
0x180016e60  lea     rdx, [rbp+57h+var_98]
0x180016e64  xor     r8d, r8d
0x180016e67  mov     qword ptr [rsp+0E0h+bIgnoreCase], r13
0x180016e6c  mov     rcx, r14
0x180016e6f  movups  xmmword ptr [rbp+57h+var_64+0Ch], xmm0
0x180016e73  movups  [rbp+57h+var_74], xmm0
0x180016e77  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180016e7d  mov     [rsp+0E0h+var_A8], r13d
0x180016e82  lea     rax, [rbp+57h+Size]
0x180016e86  mov     [rsp+0E0h+var_B0], rax
0x180016e8b  lea     r9, [rbp+57h+Size+4]
0x180016e8f  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x180016e94  lea     r8, DEVPKEY_NFP_Capabilities
0x180016e9b  lea     rdx, [rbp+57h+var_98]
0x180016e9f  mov     qword ptr [rsp+0E0h+bIgnoreCase], r13
0x180016ea4  mov     rcx, r14
0x180016ea7  call    cs:__imp_DevObjGetDeviceInterfaceProperty
0x180016ead  test    eax, eax
0x180016eaf  jnz     loc_180016FAF
0x180016eb5  mov     ebx, dword ptr [rbp+57h+Size]
0x180016eb8  cmp     ebx, 6
0x180016ebb  jb      loc_180016FAF
0x180016ec1  mov     ecx, ebx; Size
0x180016ec3  call    cs:__imp_malloc
0x180016ec9  mov     rsi, rax
0x180016ecc  test    rax, rax
0x180016ecf  jz      loc_180016FE1
0x180016ed5  mov     [rsp+0E0h+var_A8], r13d
0x180016eda  lea     r9, [rbp+57h+Size+4]
0x180016ede  mov     [rsp+0E0h+var_B0], r13
0x180016ee3  lea     r8, DEVPKEY_NFP_Capabilities
0x180016eea  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x180016eee  lea     rdx, [rbp+57h+var_98]
0x180016ef2  mov     rcx, r14
0x180016ef5  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax
0x180016efa  call    cs:__imp_DevObjGetDeviceInterfaceProperty
0x180016f00  test    eax, eax
0x180016f02  jz      loc_180016F8B
0x180016f08  cmp     dword ptr [rbp+57h+Size+4], 2012h
0x180016f0f  jnz     short loc_180016F8B
0x180016f11  mov     ecx, dword ptr [rbp+57h+Size]
0x180016f14  mov     rbx, rsi
0x180016f17  shr     rcx, 1
0x180016f1a  mov     [rsi+rcx*2-2], r13w
0x180016f20  mov     ecx, dword ptr [rbp+57h+Size]
0x180016f23  shr     rcx, 1
0x180016f26  mov     [rsi+rcx*2-4], r13w
0x180016f2c  cmp     [rsi], r13w
0x180016f30  jz      short loc_180016F8B
0x180016f32  or      r9d, 0FFFFFFFFh; cchCount2
0x180016f36  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x180016f3e  or      edx, r9d; cchCount1
0x180016f41  lea     r8, String2; "StandardNfc"
0x180016f48  mov     rcx, rbx; lpString1
0x180016f4b  call    cs:__imp_CompareStringOrdinal
0x180016f51  cmp     eax, 2
0x180016f54  jnz     short loc_180016F9D
0x180016f56  mov     r12b, 1
0x180016f59  mov     r10, cs:WPP_GLOBAL_Control
0x180016f60  cmp     r10, rdi
0x180016f63  jz      short loc_180016F8B
0x180016f65  cmp     byte ptr [r10+19h], 5
0x180016f6a  jb      short loc_180016F8B
0x180016f6c  xor     ecx, ecx; int
0x180016f6e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016f73  mov     rcx, [r10+10h]
0x180016f77  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180016f7e  mov     edx, 0BBh
0x180016f83  mov     r9, rax
0x180016f86  call    WPP_SF_s
0x180016f8b  mov     rcx, rsi; Block
0x180016f8e  call    cs:__imp_free
0x180016f94  mov     rsi, r13
0x180016f97  jmp     short loc_180016FE1
0x180016f99  add     rbx, 2
0x180016f9d  cmp     [rbx], r13w
0x180016fa1  jnz     short loc_180016F99
0x180016fa3  add     rbx, 2
0x180016fa7  cmp     [rbx], r13w
0x180016fab  jnz     short loc_180016F32
0x180016fad  jmp     short loc_180016F8B
0x180016faf  mov     r10, cs:WPP_GLOBAL_Control
0x180016fb6  cmp     r10, rdi
0x180016fb9  jz      short loc_180016FE1
0x180016fbb  cmp     byte ptr [r10+19h], 2
0x180016fc0  jb      short loc_180016FE1
0x180016fc2  xor     ecx, ecx; int
0x180016fc4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016fc9  mov     rcx, [r10+10h]
0x180016fcd  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180016fd4  mov     edx, 0BCh
0x180016fd9  mov     r9, rax
0x180016fdc  call    WPP_SF_s
0x180016fe1  inc     r15b
0x180016fe4  cmp     r15b, 0Ah
0x180016fe8  jb      loc_180016E0D
0x180016fee  jmp     short loc_180017022
0x180016ff0  mov     r10, cs:WPP_GLOBAL_Control
0x180016ff7  cmp     r10, rdi
0x180016ffa  jz      short loc_180017022
0x180016ffc  cmp     byte ptr [r10+19h], 2
0x180017001  jb      short loc_180017022
0x180017003  xor     ecx, ecx; int
0x180017005  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001700a  mov     edx, 0BAh
0x18001700f  mov     rcx, [r10+10h]
0x180017013  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001701a  mov     r9, rax
0x18001701d  call    WPP_SF_s
0x180017022  mov     rcx, rsi; Block
0x180017025  call    cs:__imp_free
0x18001702b  mov     al, r12b
0x18001702e  mov     rcx, [rbp+57h+var_48]
0x180017032  xor     rcx, rsp; StackCookie
0x180017035  call    __security_check_cookie
0x18001703a  add     rsp, 0A8h
0x180017041  pop     r15
0x180017043  pop     r14
0x180017045  pop     r13
0x180017047  pop     r12
0x180017049  pop     rdi
0x18001704a  pop     rsi
0x18001704b  pop     rbx
0x18001704c  pop     rbp
0x18001704d  retn
```
