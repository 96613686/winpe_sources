# CBiometricUnit::OpenSensor(void)

- ea: `0x1800310c4`
- end: `0x180031280`
- name: `?OpenSensor@CBiometricUnit@@QEAAJXZ`
- size: `444`
- prototype: `__int64 __fastcall(CBiometricUnit *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180030d14`
- `0x18004c810`

## callees

- `0x180014894`
- `0x1800310c4`
- `0x180055928`
- `0x180068f60`
- `0x180078928`
- `0x180078c18`
- `0x180079a00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031237`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031198`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031198`
- `api-ms-win-service-private-l1-1-0!I_ScRegisterDeviceNotification` at `0x180031225`
- `api-ms-win-service-private-l1-1-0!I_ScRegisterDeviceNotification` at `0x180031225`

## string_xrefs

- `0x1800310e9`: `CBiometricUnit::OpenSensor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CBiometricUnit::OpenSensor(CBiometricUnit *this)
{
  signed int v2; // ebx
  const WCHAR *v3; // rax
  signed int LastError; // eax
  __int64 v5; // rax
  __int64 v6; // rax
  signed int v7; // eax
  signed int v9; // [rsp+40h] [rbp-39h] BYREF
  int v10; // [rsp+44h] [rbp-35h] BYREF
  _BYTE v11[8]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v12[32]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v13; // [rsp+70h] [rbp-9h] BYREF
  __int128 v14; // [rsp+80h] [rbp+7h]
  __int128 v15; // [rsp+90h] [rbp+17h]
  __int64 v16; // [rsp+A0h] [rbp+27h]
  char v17[32]; // [rsp+A8h] [rbp+2Fh] BYREF

  v9 = 0;
  strcpy(v17, "CBiometricUnit::OpenSensor");
  v10 = 0;
  lambda_ec8d93457b2ae6058a4af8c847b09164_::_lambda_ec8d93457b2ae6058a4af8c847b09164_(
    (unsigned int)v12,
    (unsigned int)v17,
    (unsigned int)&v10,
    (unsigned int)&v9,
    (__int64)this);
  lambda_810afca0d942ac464369c1a107b3912b_::operator()(v12);
  v10 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(v11, v12);
  if ( *((char *)this + 96) >= 0 )
  {
    if ( *(_QWORD *)(*((_QWORD *)this + 338) + 16LL) == -1
      && (v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 2672),
          *(_QWORD *)(*((_QWORD *)this + 338) + 16LL) = CreateFileW(v3, 0xC0000000, 0, 0, 3u, 0x40000000u, 0),
          *(_QWORD *)(*((_QWORD *)this + 338) + 16LL) == -1) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v9 = v2;
    }
    else
    {
      v2 = v9;
    }
    if ( v2 >= 0 && !*((_QWORD *)this + 346) )
    {
      v13 = 0;
      *(_QWORD *)&v13 = 0x600000038LL;
      v16 = 0;
      v5 = *((_QWORD *)this + 338);
      v14 = 0;
      v15 = 0;
      *(_QWORD *)&v14 = *(_QWORD *)(v5 + 16);
      v6 = I_ScRegisterDeviceNotification(*((_QWORD *)this + 345), &v13, 1);
      *((_QWORD *)this + 346) = v6;
      if ( v6 )
      {
        v2 = v9;
      }
      else
      {
        v7 = GetLastError();
        v2 = v7;
        if ( v7 > 0 )
          v2 = (unsigned __int16)v7 | 0x80070000;
        v9 = v2;
      }
    }
  }
  else
  {
    v2 = -2146861012;
  }
  WppTraceUnwinder__lambda_810afca0d942ac464369c1a107b3912b____::_WppTraceUnwinder__lambda_810afca0d942ac464369c1a107b3912b____(v11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800310c4  mov     [rsp-8+arg_8], rbx
0x1800310c9  mov     [rsp-8+arg_10], rdi
0x1800310ce  push    rbp
0x1800310cf  lea     rbp, [rsp-57h]
0x1800310d4  sub     rsp, 0D0h
0x1800310db  mov     rax, cs:__security_cookie
0x1800310e2  xor     rax, rsp
0x1800310e5  mov     [rbp+57h+var_8], rax
0x1800310e9  movups  xmm0, xmmword ptr cs:aCbiometricunit_0; "CBiometricUnit::OpenSensor"
0x1800310f0  mov     rdi, rcx
0x1800310f3  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rcx
0x1800310f8  movups  xmm1, xmmword ptr cs:aCbiometricunit_0+0Bh; "nit::OpenSensor"
0x1800310ff  lea     r9, [rbp+57h+var_90]
0x180031103  mov     [rbp+57h+var_90], 0
0x18003110a  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x18003110e  lea     r8, [rbp+57h+var_8C]
0x180031112  mov     [rbp+57h+var_8C], 0
0x180031119  lea     rdx, [rbp+57h+var_28]
0x18003111d  lea     rcx, [rbp+57h+var_80]
0x180031121  movups  xmmword ptr [rbp+57h+var_28+0Bh], xmm1
0x180031125  call    _lambda_ec8d93457b2ae6058a4af8c847b09164____lambda_ec8d93457b2ae6058a4af8c847b09164_
0x18003112a  lea     rcx, [rbp+57h+var_80]
0x18003112e  call    _lambda_810afca0d942ac464369c1a107b3912b___operator__
0x180031133  lea     rdx, [rbp+57h+var_80]
0x180031137  mov     [rbp+57h+var_8C], 1
0x18003113e  lea     rcx, [rbp+57h+var_88]
0x180031142  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x180031147  test    byte ptr [rdi+60h], 80h
0x18003114b  jz      short loc_180031157
0x18003114d  mov     ebx, 8009802Ch
0x180031152  jmp     loc_180031254
0x180031157  mov     rax, [rdi+0A90h]
0x18003115e  cmp     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x180031163  jnz     short loc_1800311D1
0x180031165  lea     rcx, [rdi+0A70h]
0x18003116c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031171  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18003117a  mov     rcx, rax; lpFileName
0x18003117d  mov     [rsp+0D0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180031185  xor     r9d, r9d; lpSecurityAttributes
0x180031188  xor     r8d, r8d; dwShareMode
0x18003118b  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180031193  mov     edx, 0C0000000h; dwDesiredAccess
0x180031198  call    cs:__imp_CreateFileW
0x18003119e  mov     rcx, [rdi+0A90h]
0x1800311a5  mov     [rcx+10h], rax
0x1800311a9  mov     rax, [rdi+0A90h]
0x1800311b0  cmp     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1800311b5  jnz     short loc_1800311D1
0x1800311b7  call    cs:__imp_GetLastError
0x1800311bd  mov     ebx, eax
0x1800311bf  test    eax, eax
0x1800311c1  jle     short loc_1800311CC
0x1800311c3  movzx   ebx, ax
0x1800311c6  or      ebx, 80070000h
0x1800311cc  mov     [rbp+57h+var_90], ebx
0x1800311cf  jmp     short loc_1800311D4
0x1800311d1  mov     ebx, [rbp+57h+var_90]
0x1800311d4  test    ebx, ebx
0x1800311d6  js      short loc_180031254
0x1800311d8  cmp     qword ptr [rdi+0AD0h], 0
0x1800311e0  jnz     short loc_180031254
0x1800311e2  xorps   xmm0, xmm0
0x1800311e5  lea     rdx, [rbp+57h+var_60]
0x1800311e9  movups  [rbp+57h+var_60], xmm0
0x1800311ed  xor     eax, eax
0x1800311ef  mov     dword ptr [rbp+57h+var_60], 38h ; '8'
0x1800311f6  mov     [rbp+57h+var_30], rax
0x1800311fa  mov     r8d, 1
0x180031200  mov     rax, [rdi+0A90h]
0x180031207  movups  [rbp+57h+var_50], xmm0
0x18003120b  mov     dword ptr [rbp+57h+var_60+4], 6
0x180031212  movups  [rbp+57h+var_40], xmm0
0x180031216  mov     rcx, [rax+10h]
0x18003121a  mov     qword ptr [rbp+57h+var_50], rcx
0x18003121e  mov     rcx, [rdi+0AC8h]
0x180031225  call    cs:__imp_I_ScRegisterDeviceNotification
0x18003122b  mov     [rdi+0AD0h], rax
0x180031232  test    rax, rax
0x180031235  jnz     short loc_180031251
0x180031237  call    cs:__imp_GetLastError
0x18003123d  mov     ebx, eax
0x18003123f  test    eax, eax
0x180031241  jle     short loc_18003124C
0x180031243  movzx   ebx, ax
0x180031246  or      ebx, 80070000h
0x18003124c  mov     [rbp+57h+var_90], ebx
0x18003124f  jmp     short loc_180031254
0x180031251  mov     ebx, [rbp+57h+var_90]
0x180031254  lea     rcx, [rbp+57h+var_88]
0x180031258  call    WppTraceUnwinder__lambda_810afca0d942ac464369c1a107b3912b_______WppTraceUnwinder__lambda_810afca0d942ac464369c1a107b3912b____
0x18003125d  mov     eax, ebx
0x18003125f  mov     rcx, [rbp+57h+var_8]
0x180031263  xor     rcx, rsp; StackCookie
0x180031266  call    __security_check_cookie
0x18003126b  lea     r11, [rsp+0D0h+var_s0]
0x180031273  mov     rbx, [r11+18h]
0x180031277  mov     rdi, [r11+20h]
0x18003127b  mov     rsp, r11
0x18003127e  pop     rbp
0x18003127f  retn
```
