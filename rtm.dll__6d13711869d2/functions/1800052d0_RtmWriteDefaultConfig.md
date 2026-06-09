# RtmWriteDefaultConfig

- ea: `0x1800052d0`
- end: `0x18000551f`
- name: `RtmWriteDefaultConfig`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007a34`

## callees

- `0x180002c5c`
- `0x180004b50`
- `0x1800052d0`
- `0x180005530`
- `0x180007a34`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## string_xrefs

- `0x180005348`: `Entered: RtmWriteDefaultConfig`
- `0x1800053a2`: `Default Config: Error %d writing instance key`
- `0x1800054cf`: `Leaving: RtmWriteDefaultConfig`
- `0x180005465`: `Default Config: Error %d writing address family subkey`

## pseudocode

```c
__int64 RtmWriteDefaultConfig()
{
  __int64 v0; // r8
  __int64 result; // rax
  unsigned int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  char v5; // cl
  __int64 v6; // rax
  bool v7; // zf
  unsigned int v8; // eax
  __int64 v9; // rax
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h]
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-A0h]
  __int64 v14; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v11 = 0;
  v15 = 0;
  v10 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( (_DWORD)qword_18002BD00 || (result = RtmApiStartup(), !(_DWORD)result) )
  {
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v14 = 62;
      v13 = L"Entered: RtmWriteDefaultConfig";
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RRAS_RTM_TRACE_INFO,
        v0,
        2u,
        &v12);
    }
    v2 = RtmWriteInstanceConfig();
    v4 = v2;
    if ( v2 )
    {
      v5 = byte_18002BD1A;
      if ( (byte_18002BD1A & 4) != 0 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v15, L"Default Config: Error %d writing instance key", v2);
        v5 = byte_18002BD1A;
        if ( (byte_18002BD1A & 4) != 0 )
        {
          v6 = -1;
          do
            ++v6;
          while ( *(_WORD *)&v16[2 * v6 - 4] );
          v14 = (unsigned int)(2 * v6 + 2);
          v13 = (const wchar_t *)&v15;
          McGenEventWrite_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RRAS_RTM_TRACE_ERROR,
            v3,
            2u,
            &v12);
          v5 = byte_18002BD1A;
        }
      }
      v7 = (v5 & 8) == 0;
    }
    else
    {
      *(_QWORD *)&v10 = 0x300000004LL;
      *((_QWORD *)&v10 + 1) = 0x300000005LL;
      v11 = 0x1000000019LL;
      v8 = RtmWriteAddressFamilyConfig(0, 2u, &v10);
      v4 = v8;
      if ( v8 )
      {
        if ( (byte_18002BD1A & 4) != 0 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"Default Config: Error %d writing address family subkey", v8);
          if ( (byte_18002BD1A & 4) != 0 )
          {
            v9 = -1;
            do
              ++v9;
            while ( *(_WORD *)&v16[2 * v9 - 4] );
            v14 = (unsigned int)(2 * v9 + 2);
            v13 = (const wchar_t *)&v15;
            McGenEventWrite_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RRAS_RTM_TRACE_ERROR,
              v3,
              2u,
              &v12);
          }
        }
      }
      v7 = (byte_18002BD1A & 8) == 0;
    }
    if ( !v7 )
    {
      v14 = 62;
      v13 = L"Leaving: RtmWriteDefaultConfig";
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RRAS_RTM_TRACE_INFO,
        v3,
        2u,
        &v12);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800052d0  push    rbp
0x1800052d2  push    rbx
0x1800052d3  push    rsi
0x1800052d4  push    rdi
0x1800052d5  push    r14
0x1800052d7  lea     rbp, [rsp-780h]
0x1800052df  sub     rsp, 880h
0x1800052e6  mov     rax, cs:__security_cookie
0x1800052ed  xor     rax, rsp
0x1800052f0  mov     [rbp+7A0h+var_30], rax
0x1800052f7  xorps   xmm0, xmm0
0x1800052fa  lea     rcx, [rsp+8A0h+var_82C]; void *
0x1800052ff  xor     eax, eax
0x180005301  xor     edi, edi
0x180005303  xor     edx, edx; Val
0x180005305  mov     [rsp+8A0h+var_858], rax
0x18000530a  mov     r8d, 7FCh; Size
0x180005310  mov     [rsp+8A0h+var_830], edi
0x180005314  movups  [rsp+8A0h+var_868], xmm0
0x180005319  call    memset_0
0x18000531e  cmp     dword ptr cs:qword_18002BD00, edi
0x180005324  jnz     short loc_180005333
0x180005326  call    RtmApiStartup
0x18000532b  test    eax, eax
0x18000532d  jnz     loc_180005502
0x180005333  test    cs:byte_18002BD1A, 8
0x18000533a  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005341  mov     esi, 2
0x180005346  jz      short loc_180005379
0x180005348  lea     rax, aEnteredRtmwrit_0; "Entered: RtmWriteDefaultConfig"
0x18000534f  mov     [rsp+8A0h+var_838], 3Eh ; '>'
0x180005358  mov     [rsp+8A0h+var_840], rax
0x18000535d  lea     rdx, RRAS_RTM_TRACE_INFO
0x180005364  lea     rax, [rsp+8A0h+var_850]
0x180005369  mov     r9d, esi
0x18000536c  mov     rcx, r14
0x18000536f  mov     [rsp+8A0h+var_880], rax
0x180005374  call    McGenEventWrite_EventWriteTransfer
0x180005379  xor     ecx, ecx
0x18000537b  lea     rdx, [rsp+8A0h+var_870]
0x180005380  call    RtmWriteInstanceConfig
0x180005385  mov     ebx, eax
0x180005387  test    eax, eax
0x180005389  jz      loc_180005413
0x18000538f  mov     cl, cs:byte_18002BD1A
0x180005395  test    cl, 4
0x180005398  jz      short loc_18000540B
0x18000539a  mov     r8d, eax
0x18000539d  mov     word ptr [rsp+8A0h+var_830], di
0x1800053a2  lea     rdx, aDefaultConfigE_0; "Default Config: Error %d writing instan"...
0x1800053a9  lea     rcx, [rsp+8A0h+var_830]
0x1800053ae  call    FormatRRASErrorString
0x1800053b3  mov     cl, cs:byte_18002BD1A
0x1800053b9  test    cl, 4
0x1800053bc  jz      short loc_18000540B
0x1800053be  lea     rcx, [rsp+8A0h+var_830]
0x1800053c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800053c7  inc     rax
0x1800053ca  cmp     [rcx+rax*2], di
0x1800053ce  jnz     short loc_1800053C7
0x1800053d0  lea     eax, ds:2[rax*2]
0x1800053d7  mov     dword ptr [rsp+8A0h+var_838+4], edi
0x1800053db  lea     rcx, [rsp+8A0h+var_830]
0x1800053e0  mov     dword ptr [rsp+8A0h+var_838], eax
0x1800053e4  lea     rax, [rsp+8A0h+var_850]
0x1800053e9  mov     [rsp+8A0h+var_840], rcx
0x1800053ee  mov     r9d, esi
0x1800053f1  mov     [rsp+8A0h+var_880], rax
0x1800053f6  lea     rdx, RRAS_RTM_TRACE_ERROR
0x1800053fd  mov     rcx, r14
0x180005400  call    McGenEventWrite_EventWriteTransfer
0x180005405  mov     cl, cs:byte_18002BD1A
0x18000540b  test    cl, 8
0x18000540e  jmp     loc_1800054CD
0x180005413  mov     eax, 3
0x180005418  mov     dword ptr [rsp+8A0h+var_868], 4
0x180005420  mov     edx, esi
0x180005422  mov     dword ptr [rsp+8A0h+var_868+0Ch], eax
0x180005426  xor     ecx, ecx
0x180005428  mov     dword ptr [rsp+8A0h+var_868+4], eax
0x18000542c  lea     r8, [rsp+8A0h+var_868]
0x180005431  mov     dword ptr [rsp+8A0h+var_868+8], 5
0x180005439  mov     dword ptr [rsp+8A0h+var_858], 19h
0x180005441  mov     dword ptr [rsp+8A0h+var_858+4], 10h
0x180005449  call    RtmWriteAddressFamilyConfig
0x18000544e  mov     ebx, eax
0x180005450  test    eax, eax
0x180005452  jz      short loc_1800054C6
0x180005454  test    cs:byte_18002BD1A, 4
0x18000545b  jz      short loc_1800054C6
0x18000545d  mov     r8d, eax
0x180005460  mov     word ptr [rsp+8A0h+var_830], di
0x180005465  lea     rdx, aDefaultConfigE; "Default Config: Error %d writing addres"...
0x18000546c  lea     rcx, [rsp+8A0h+var_830]
0x180005471  call    FormatRRASErrorString
0x180005476  test    cs:byte_18002BD1A, 4
0x18000547d  jz      short loc_1800054C6
0x18000547f  lea     rcx, [rsp+8A0h+var_830]
0x180005484  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005488  inc     rax
0x18000548b  cmp     [rcx+rax*2], di
0x18000548f  jnz     short loc_180005488
0x180005491  lea     eax, ds:2[rax*2]
0x180005498  mov     dword ptr [rsp+8A0h+var_838+4], edi
0x18000549c  lea     rcx, [rsp+8A0h+var_830]
0x1800054a1  mov     dword ptr [rsp+8A0h+var_838], eax
0x1800054a5  lea     rax, [rsp+8A0h+var_850]
0x1800054aa  mov     [rsp+8A0h+var_840], rcx
0x1800054af  mov     r9d, esi
0x1800054b2  mov     [rsp+8A0h+var_880], rax
0x1800054b7  lea     rdx, RRAS_RTM_TRACE_ERROR
0x1800054be  mov     rcx, r14
0x1800054c1  call    McGenEventWrite_EventWriteTransfer
0x1800054c6  test    cs:byte_18002BD1A, 8
0x1800054cd  jz      short loc_180005500
0x1800054cf  lea     rax, aLeavingRtmwrit; "Leaving: RtmWriteDefaultConfig"
0x1800054d6  mov     [rsp+8A0h+var_838], 3Eh ; '>'
0x1800054df  mov     [rsp+8A0h+var_840], rax
0x1800054e4  lea     rdx, RRAS_RTM_TRACE_INFO
0x1800054eb  lea     rax, [rsp+8A0h+var_850]
0x1800054f0  mov     r9d, esi
0x1800054f3  mov     rcx, r14
0x1800054f6  mov     [rsp+8A0h+var_880], rax
0x1800054fb  call    McGenEventWrite_EventWriteTransfer
0x180005500  mov     eax, ebx
0x180005502  mov     rcx, [rbp+7A0h+var_30]
0x180005509  xor     rcx, rsp; StackCookie
0x18000550c  call    __security_check_cookie
0x180005511  add     rsp, 880h
0x180005518  pop     r14
0x18000551a  pop     rdi
0x18000551b  pop     rsi
0x18000551c  pop     rbx
0x18000551d  pop     rbp
0x18000551e  retn
```
