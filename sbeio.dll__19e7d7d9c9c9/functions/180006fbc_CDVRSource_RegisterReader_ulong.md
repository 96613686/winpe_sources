# CDVRSource::RegisterReader(ulong)

- ea: `0x180006fbc`
- end: `0x18000723a`
- name: `?RegisterReader@CDVRSource@@IEAAJK@Z`
- size: `638`
- prototype: `__int64 __fastcall(CDVRSource *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005df0`

## callees

- `0x1800015f0`
- `0x1800024c4`
- `0x1800027c4`
- `0x1800050cc`
- `0x18000569c`
- `0x180006fbc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800070fd`
- `KERNEL32!CreateEventW` at `0x1800070fd`
- `KERNEL32!CloseHandle` at `0x180007120`
- `KERNEL32!CloseHandle` at `0x1800071f5`
- `KERNEL32!CloseHandle` at `0x180007205`
- `KERNEL32!CloseHandle` at `0x18002a67e`
- `KERNEL32!CloseHandle` at `0x18002a68e`
- `KERNEL32!CloseHandle` at `0x180007120`
- `KERNEL32!CloseHandle` at `0x1800071f5`
- `KERNEL32!CloseHandle` at `0x180007205`
- `KERNEL32!CloseHandle` at `0x18002a67e`
- `KERNEL32!CloseHandle` at `0x18002a68e`
- `KERNEL32!GetLastError` at `0x18000710b`
- `KERNEL32!GetLastError` at `0x18000710b`

## pseudocode

```c
__int64 __fastcall CDVRSource::RegisterReader(CDVRSource *this, unsigned int a2, enum _ACCESS_MODE a3)
{
  __int64 v3; // r13
  HANDLE EventW; // rdi
  ULONG v6; // ecx
  int v7; // eax
  int v8; // ebx
  int i; // r14d
  struct _SECURITY_ATTRIBUTES *v10; // rcx
  DWORD LastError; // eax
  __int64 v12; // r12
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-F8h]
  struct _GUID hObject; // [rsp+48h] [rbp-D0h] BYREF
  int v18; // [rsp+58h] [rbp-C0h]
  void *v19[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _ACL *v20; // [rsp+70h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+88h] [rbp-90h]
  WCHAR Name[40]; // [rsp+90h] [rbp-88h] BYREF

  v3 = a2;
  v20 = 0;
  v19[0] = 0;
  v21 = 0;
  v22 = 0;
  EventW = 0;
  *(_QWORD *)hObject.Data4 = 0;
  *(_QWORD *)&hObject.Data1 = 0;
  v6 = *((_DWORD *)this + 47);
  if ( v6 )
  {
    v7 = CreateACL(v6, *((void ***)this + 29), a3, 2031619, (enum _ACCESS_MODE)v16, 2u, &v20, v19);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      goto LABEL_21;
    }
    LODWORD(v21) = 24;
    *((void **)&v21 + 1) = v19[0];
    LODWORD(v22) = 0;
  }
  for ( i = 1; ; ++i )
  {
    v18 = i;
    if ( i == -1 )
      break;
    LODWORD(v16) = i;
    v8 = StringCchPrintfW(Name, 0x28u, L"%s%u", L"Global\\_MS_TSDVRASF_EVENT_", v16);
    if ( v8 < 0 )
      goto LABEL_21;
    v10 = (struct _SECURITY_ATTRIBUTES *)&v21;
    if ( !*((_DWORD *)this + 47) )
      v10 = 0;
    EventW = CreateEventW(v10, 0, 0, Name);
    *(_QWORD *)hObject.Data4 = EventW;
    LastError = GetLastError();
    if ( EventW )
    {
      if ( LastError != 183 )
        break;
      CloseHandle(EventW);
      EventW = 0;
      *(_QWORD *)hObject.Data4 = 0;
    }
  }
  if ( *((_DWORD *)this + 47) )
    FreeSecurityDescriptors(&v20, v19);
  if ( EventW )
  {
    v12 = *((_QWORD *)this + 8);
    *(_OWORD *)v19 = 0;
    v8 = DVRSourceSink::CreateReaderIdEvent(*((_DWORD *)this + 47), *((void ***)this + 29), (UUID *)v19, &hObject);
    if ( v8 >= 0 )
    {
      v13 = 5 * (v3 + 2);
      *(_OWORD *)(v12 + 8 * v13) = *(_OWORD *)v19;
      ++*(_DWORD *)(v12 + 8 * v13 + 16);
      *((_QWORD *)this + 17) = *(_QWORD *)&hObject.Data1;
      *((_QWORD *)this + 14) = EventW;
      v14 = 5 * v3;
      *(_DWORD *)(*((_QWORD *)this + 8) + 8 * v14 + 72) = i;
      *((_DWORD *)this + 42) = v3;
      *(_DWORD *)(*((_QWORD *)this + 8) + 8 * v14 + 76) = 0;
      v8 = 0;
    }
  }
  else
  {
    v8 = -2147467259;
  }
LABEL_21:
  if ( v8 < 0 )
  {
    if ( EventW )
      CloseHandle(EventW);
    if ( *(_QWORD *)&hObject.Data1 )
      CloseHandle(*(HANDLE *)&hObject.Data1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006fbc  mov     [rsp+arg_10], rbx
0x180006fc1  mov     [rsp+arg_18], rsi
0x180006fc6  push    rdi
0x180006fc7  push    r12
0x180006fc9  push    r13
0x180006fcb  push    r14
0x180006fcd  push    r15
0x180006fcf  sub     rsp, 0F0h
0x180006fd6  mov     rax, cs:__security_cookie
0x180006fdd  xor     rax, rsp
0x180006fe0  mov     [rsp+118h+var_38], rax
0x180006fe8  mov     r13d, edx
0x180006feb  mov     rsi, rcx
0x180006fee  xor     r12d, r12d
0x180006ff1  mov     [rsp+118h+var_C8], r12
0x180006ff6  mov     [rsp+118h+var_A8], r12
0x180006ffb  mov     [rsp+118h+var_B8], r12
0x180007000  xorps   xmm0, xmm0
0x180007003  xor     eax, eax
0x180007005  movups  [rsp+118h+var_A0], xmm0
0x18000700a  mov     [rsp+118h+var_90], rax
0x180007012  mov     [rsp+118h+var_D8], r12d
0x180007017  mov     [rsp+118h+hObject], r12
0x18000701c  mov     edi, r12d
0x18000701f  mov     [rsp+118h+var_C8], r12
0x180007024  mov     [rsp+118h+hObject], r12
0x180007029  mov     ecx, [rcx+0BCh]; cCountOfExplicitEntries
0x18000702f  test    ecx, ecx
0x180007031  jz      short loc_180007098
0x180007033  lea     rax, [rsp+118h+var_B8]
0x180007038  mov     [rsp+118h+var_E0], rax; void **
0x18000703d  lea     rax, [rsp+118h+var_A8]
0x180007042  mov     [rsp+118h+var_E8], rax; struct _ACL **
0x180007047  mov     [rsp+118h+var_F0], 2; unsigned int
0x18000704f  mov     r9d, 1F0003h; unsigned int
0x180007055  mov     rdx, [rsi+0E8h]; void **
0x18000705c  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180007061  mov     ebx, eax
0x180007063  test    eax, eax
0x180007065  jz      short loc_18000707B
0x180007067  jle     loc_1800071E5
0x18000706d  movzx   ebx, ax
0x180007070  or      ebx, 80070000h
0x180007076  jmp     loc_1800071E5
0x18000707b  mov     dword ptr [rsp+118h+var_A0], 18h
0x180007083  mov     rax, [rsp+118h+var_B8]
0x180007088  mov     qword ptr [rsp+118h+var_A0+8], rax
0x180007090  mov     dword ptr [rsp+118h+var_90], r12d
0x180007098  mov     r14d, 1
0x18000709e  mov     [rsp+118h+var_C0], r14d
0x1800070a3  cmp     r14d, 0FFFFFFFFh
0x1800070a7  jnb     loc_180007136
0x1800070ad  mov     dword ptr [rsp+118h+var_F8], r14d
0x1800070b2  lea     r9, aGlobalMsTsdvra_0; "Global\\_MS_TSDVRASF_EVENT_"
0x1800070b9  lea     r8, aSU; "%s%u"
0x1800070c0  mov     edx, 28h ; '('; unsigned __int64
0x1800070c5  lea     rcx, [rsp+118h+Name]; unsigned __int16 *
0x1800070cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800070d2  mov     ebx, eax
0x1800070d4  mov     [rsp+118h+var_D8], eax
0x1800070d8  test    eax, eax
0x1800070da  js      loc_1800071E9
0x1800070e0  lea     rcx, [rsp+118h+var_A0]
0x1800070e5  cmp     [rsi+0BCh], r12d
0x1800070ec  cmovbe  rcx, r12; lpEventAttributes
0x1800070f0  lea     r9, [rsp+118h+Name]; lpName
0x1800070f8  xor     r8d, r8d; bInitialState
0x1800070fb  xor     edx, edx; bManualReset
0x1800070fd  call    cs:__imp_CreateEventW
0x180007103  mov     rdi, rax
0x180007106  mov     [rsp+118h+var_C8], rax
0x18000710b  call    cs:__imp_GetLastError
0x180007111  test    rdi, rdi
0x180007114  jz      short loc_18000712E
0x180007116  cmp     eax, 0B7h
0x18000711b  jnz     short loc_180007136
0x18000711d  mov     rcx, rdi; hObject
0x180007120  call    cs:__imp_CloseHandle
0x180007126  mov     rdi, r12
0x180007129  mov     [rsp+118h+var_C8], r12
0x18000712e  inc     r14d
0x180007131  jmp     loc_18000709E
0x180007136  cmp     [rsi+0BCh], r12d
0x18000713d  jbe     short loc_18000714E
0x18000713f  lea     rdx, [rsp+118h+var_B8]; void **
0x180007144  lea     rcx, [rsp+118h+var_A8]; struct _ACL **
0x180007149  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x18000714e  test    rdi, rdi
0x180007151  jnz     short loc_18000715D
0x180007153  mov     ebx, 80004005h
0x180007158  jmp     loc_1800071E5
0x18000715d  mov     r12, [rsi+40h]
0x180007161  xorps   xmm0, xmm0
0x180007164  movups  xmmword ptr [rsp+118h+var_B8], xmm0
0x180007169  lea     r9, [rsp+118h+hObject]; struct _GUID *
0x18000716e  lea     r8, [rsp+118h+var_B8]; void **
0x180007173  mov     rdx, [rsi+0E8h]; void **
0x18000717a  mov     ecx, [rsi+0BCh]; cCountOfExplicitEntries
0x180007180  call    ?CreateReaderIdEvent@DVRSourceSink@@YAJKPEAPEAXPEAU_GUID@@0@Z; DVRSourceSink::CreateReaderIdEvent(ulong,void * *,_GUID *,void * *)
0x180007185  mov     ebx, eax
0x180007187  test    eax, eax
0x180007189  js      short loc_1800071A3
0x18000718b  lea     rax, [r13+2]
0x18000718f  lea     rax, [rax+rax*4]
0x180007193  movups  xmm0, xmmword ptr [rsp+118h+var_B8]
0x180007198  movdqu  xmmword ptr [r12+rax*8], xmm0
0x18000719e  inc     dword ptr [r12+rax*8+10h]
0x1800071a3  mov     [rsp+118h+var_D8], ebx
0x1800071a7  xor     r12d, r12d
0x1800071aa  test    ebx, ebx
0x1800071ac  js      short loc_1800071E9
0x1800071ae  mov     rax, [rsp+118h+hObject]
0x1800071b3  mov     [rsi+88h], rax
0x1800071ba  mov     [rsi+70h], rdi
0x1800071be  lea     rcx, ds:0[r13*4]
0x1800071c6  add     rcx, r13
0x1800071c9  mov     rax, [rsi+40h]
0x1800071cd  mov     [rax+rcx*8+48h], r14d
0x1800071d2  mov     [rsi+0A8h], r13d
0x1800071d9  mov     rax, [rsi+40h]
0x1800071dd  mov     [rax+rcx*8+4Ch], r12d
0x1800071e2  mov     ebx, r12d
0x1800071e5  mov     [rsp+118h+var_D8], ebx
0x1800071e9  test    ebx, ebx
0x1800071eb  jns     short loc_18000720B
0x1800071ed  test    rdi, rdi
0x1800071f0  jz      short loc_1800071FB
0x1800071f2  mov     rcx, rdi; hObject
0x1800071f5  call    cs:__imp_CloseHandle
0x1800071fb  mov     rcx, [rsp+118h+hObject]; hObject
0x180007200  test    rcx, rcx
0x180007203  jz      short loc_18000720B
0x180007205  call    cs:__imp_CloseHandle
0x18000720b  mov     eax, ebx
0x18000720d  mov     rcx, [rsp+118h+var_38]
0x180007215  xor     rcx, rsp; StackCookie
0x180007218  call    __security_check_cookie
0x18000721d  lea     r11, [rsp+118h+var_28]
0x180007225  mov     rbx, [r11+40h]
0x180007229  mov     rsi, [r11+48h]
0x18000722d  mov     rsp, r11
0x180007230  pop     r15
0x180007232  pop     r14
0x180007234  pop     r13
0x180007236  pop     r12
0x180007238  pop     rdi
0x180007239  retn
0x18002a666  push    rbp
0x18002a668  sub     rsp, 40h
0x18002a66c  mov     rbp, rdx
0x18002a66f  cmp     dword ptr [rbp+40h], 0
0x18002a673  jge     short loc_18002A695
0x18002a675  mov     rcx, [rbp+50h]; hObject
0x18002a679  test    rcx, rcx
0x18002a67c  jz      short loc_18002A685
0x18002a67e  call    cs:__imp_CloseHandle
0x18002a684  nop
0x18002a685  mov     rcx, [rbp+48h]; hObject
0x18002a689  test    rcx, rcx
0x18002a68c  jz      short loc_18002A695
0x18002a68e  call    cs:__imp_CloseHandle
0x18002a694  nop
0x18002a695  add     rsp, 40h
0x18002a699  pop     rbp
0x18002a69a  retn
```
