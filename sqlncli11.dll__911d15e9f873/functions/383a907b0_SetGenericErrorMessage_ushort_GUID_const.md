# SetGenericErrorMessage(ushort *,_GUID const *)

- ea: `0x383a907b0`
- end: `0x383a90950`
- name: `?SetGenericErrorMessage@@YAJPEAGPEBU_GUID@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x383a909b0`

## callees

- `0x3838434c0`
- `0x38391aed0`
- `0x38391afe0`
- `0x383a907b0`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x383a90903`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a90903`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x383a9083d`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x383a9083d`

## string_xrefs

- `0x383a907d5`: `Microsoft XML Extensions to SQL Server`

## pseudocode

```c
__int64 __fastcall SetGenericErrorMessage(unsigned __int16 *a1, const struct _GUID *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  ICreateErrorInfo *v8; // [rsp+30h] [rbp-78h] BYREF
  IErrorInfo *perrinfo; // [rsp+38h] [rbp-70h] BYREF
  _OWORD v10[4]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v11; // [rsp+80h] [rbp-28h]
  int v12; // [rsp+88h] [rbp-20h]
  wchar_t v13; // [rsp+8Ch] [rbp-1Ch]

  perrinfo = 0;
  v8 = 0;
  v10[0] = *(_OWORD *)L"Microsoft XML Extensions to SQL Server";
  v10[1] = *(_OWORD *)L"t XML Extensions to SQL Server";
  v10[2] = *(_OWORD *)L"tensions to SQL Server";
  v10[3] = *(_OWORD *)L" to SQL Server";
  v12 = *(_DWORD *)L"er";
  v11 = *(_QWORD *)L"Server";
  v13 = aMicrosoftXmlEx[38];
  v4 = CreateErrorInfo(&v8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( a2 )
      ((void (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))v8->lpVtbl->SetGUID)(v8, a2);
    if ( a1 )
      ((void (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))v8->lpVtbl->SetDescription)(v8, a1);
    ((void (__fastcall *)(ICreateErrorInfo *, _OWORD *))v8->lpVtbl->SetSource)(v8, v10);
    v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))v8->lpVtbl->QueryInterface)(
           v8,
           &IID_IErrorInfo,
           &perrinfo);
    v5 = v6;
    if ( v6 >= 0 )
    {
      SetErrorInfo(0, perrinfo);
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      bidTraceHR(off_383B43498[0], 2197513, (unsigned int)v6);
    }
  }
  else if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
  {
    bidTraceW(off_383B43498[0], 2188329, off_383B49128[0], (unsigned int)v4);
  }
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  if ( v8 )
    ((void (__fastcall *)(ICreateErrorInfo *))v8->lpVtbl->Release)(v8);
  return v5;
}

```

## disassembly

```asm
0x383a907b0  mov     r11, rsp
0x383a907b3  mov     [r11+18h], rbx
0x383a907b7  mov     [r11+20h], rsi
0x383a907bb  push    rdi
0x383a907bc  sub     rsp, 0A0h
0x383a907c3  mov     rax, cs:__security_cookie
0x383a907ca  xor     rax, rsp
0x383a907cd  mov     [rsp+0A8h+var_18], rax
0x383a907d5  movaps  xmm0, xmmword ptr cs:aMicrosoftXmlEx; "Microsoft XML Extensions to SQL Server"
0x383a907dc  movaps  xmm1, xmmword ptr cs:aMicrosoftXmlEx+10h; "t XML Extensions to SQL Server"
0x383a907e3  xor     eax, eax
0x383a907e5  mov     [r11-70h], rax
0x383a907e9  mov     [r11-78h], rax
0x383a907ed  mov     eax, dword ptr cs:aMicrosoftXmlEx+48h; "er"
0x383a907f3  movaps  [rsp+0A8h+var_68], xmm0
0x383a907f8  movaps  xmm0, xmmword ptr cs:aMicrosoftXmlEx+20h; "tensions to SQL Server"
0x383a907ff  movaps  [rsp+0A8h+var_58], xmm1
0x383a90804  mov     rdi, rcx
0x383a90807  lea     rcx, [r11-78h]; pperrinfo
0x383a9080b  mov     rsi, rdx
0x383a9080e  movaps  xmm1, xmmword ptr cs:aMicrosoftXmlEx+30h; " to SQL Server"
0x383a90815  movaps  [rsp+0A8h+var_48], xmm0
0x383a9081a  movsd   xmm0, qword ptr cs:aMicrosoftXmlEx+40h; "Server"
0x383a90822  movaps  [rsp+0A8h+var_38], xmm1
0x383a90827  mov     [r11-20h], eax
0x383a9082b  movzx   eax, word ptr cs:aMicrosoftXmlEx+4Ch; ""
0x383a90832  movsd   qword ptr [r11-28h], xmm0
0x383a90838  mov     [r11-1Ch], ax
0x383a9083d  call    cs:__imp_CreateErrorInfo
0x383a90843  mov     ebx, eax
0x383a90845  test    eax, eax
0x383a90847  jns     short loc_383A9088B
0x383a90849  test    byte ptr cs:_bidGblFlags, 2
0x383a90850  jz      loc_383A90909
0x383a90856  mov     rcx, cs:off_383B43498; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9085d  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a90864  test    rdx, rdx
0x383a90867  jz      loc_383A90909
0x383a9086d  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a90874  mov     r9d, eax
0x383a90877  mov     edx, 216429h
0x383a9087c  mov     [rsp+0A8h+var_88], 859h
0x383a90884  call    _bidTraceW
0x383a90889  jmp     short loc_383A90909
0x383a9088b  test    rsi, rsi
0x383a9088e  jz      short loc_383A9089E
0x383a90890  mov     rcx, [rsp+0A8h+var_78]
0x383a90895  mov     rdx, rsi
0x383a90898  mov     rax, [rcx]
0x383a9089b  call    qword ptr [rax+18h]
0x383a9089e  test    rdi, rdi
0x383a908a1  jz      short loc_383A908B1
0x383a908a3  mov     rcx, [rsp+0A8h+var_78]
0x383a908a8  mov     rdx, rdi
0x383a908ab  mov     rax, [rcx]
0x383a908ae  call    qword ptr [rax+28h]
0x383a908b1  mov     rcx, [rsp+0A8h+var_78]
0x383a908b6  lea     rdx, [rsp+0A8h+var_68]
0x383a908bb  mov     rax, [rcx]
0x383a908be  call    qword ptr [rax+20h]
0x383a908c1  mov     rcx, [rsp+0A8h+var_78]
0x383a908c6  lea     r8, [rsp+0A8h+perrinfo]
0x383a908cb  mov     rax, [rcx]
0x383a908ce  lea     rdx, IID_IErrorInfo
0x383a908d5  call    qword ptr [rax]
0x383a908d7  mov     ebx, eax
0x383a908d9  test    eax, eax
0x383a908db  jns     short loc_383A908FC
0x383a908dd  test    byte ptr cs:_bidGblFlags, 2
0x383a908e4  jz      short loc_383A90909
0x383a908e6  mov     rcx, cs:off_383B43498; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a908ed  mov     r8d, eax
0x383a908f0  mov     edx, 218809h
0x383a908f5  call    _bidTraceHR
0x383a908fa  jmp     short loc_383A90909
0x383a908fc  mov     rdx, [rsp+0A8h+perrinfo]; perrinfo
0x383a90901  xor     ecx, ecx; dwReserved
0x383a90903  call    cs:__imp_SetErrorInfo
0x383a90909  mov     rcx, [rsp+0A8h+perrinfo]
0x383a9090e  test    rcx, rcx
0x383a90911  jz      short loc_383A90919
0x383a90913  mov     rax, [rcx]
0x383a90916  call    qword ptr [rax+10h]
0x383a90919  mov     rcx, [rsp+0A8h+var_78]
0x383a9091e  test    rcx, rcx
0x383a90921  jz      short loc_383A90929
0x383a90923  mov     rax, [rcx]
0x383a90926  call    qword ptr [rax+10h]
0x383a90929  mov     eax, ebx
0x383a9092b  mov     rcx, [rsp+0A8h+var_18]
0x383a90933  xor     rcx, rsp; StackCookie
0x383a90936  call    __security_check_cookie
0x383a9093b  lea     r11, [rsp+0A8h+var_8]
0x383a90943  mov     rbx, [r11+20h]
0x383a90947  mov     rsi, [r11+28h]
0x383a9094b  mov     rsp, r11
0x383a9094e  pop     rdi
0x383a9094f  retn
```
