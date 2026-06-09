# CDVRRecorderWriter::InitDVRSink_(HKEY__ *,CPVRIOCounters *)

- ea: `0x18006d028`
- end: `0x18006d3a2`
- name: `?InitDVRSink_@CDVRRecorderWriter@@AEAAJPEAUHKEY__@@PEAVCPVRIOCounters@@@Z`
- size: `890`
- prototype: `int(CDVRRecorderWriter *__hidden this, HKEY, struct CPVRIOCounters *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068e48`

## callees

- `0x1800017a0`
- `0x180001c00`
- `0x18005faec`
- `0x180069780`
- `0x180069b8c`
- `0x18006d028`
- `0x180077c1c`
- `0x1800b6010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18006d336`
- `ADVAPI32!RegCloseKey` at `0x18006d336`
- `ADVAPI32!RegCreateKeyExW` at `0x18006d0b3`
- `ADVAPI32!RegCreateKeyExW` at `0x18006d0b3`
- `sbeio!DVRCreateDVRFileSink` at `0x18006d0e9`
- `sbeio!DVRCreateDVRFileSink` at `0x18006d0e9`

## string_xrefs

- `0x18006d0a9`: `IO\Writer`

## pseudocode

```c
__int64 __fastcall CDVRRecorderWriter::InitDVRSink_(CDVRRecorderWriter *this, HKEY a2, struct CPVRIOCounters *a3)
{
  int v6; // edi
  _QWORD *v7; // r15
  unsigned int v8; // edx
  void *v9; // r10
  CPVRAsyncWriterCOM *v10; // r14
  int v12; // [rsp+70h] [rbp-88h]
  int v13; // [rsp+74h] [rbp-84h] BYREF
  void **v14; // [rsp+78h] [rbp-80h] BYREF
  int v15; // [rsp+80h] [rbp-78h]
  int v16; // [rsp+84h] [rbp-74h]
  int v17; // [rsp+88h] [rbp-70h]
  _DWORD v18[6]; // [rsp+90h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-48h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-40h] BYREF

  CPVREmptyProf::CPVREmptyProf((CPVREmptyProf *)v18);
  hKey = 0;
  v20 = 0;
  v21 = 0;
  v6 = RegCreateKeyExW(a2, L"IO\\Writer", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  v13 = v6;
  if ( v6 )
    hKey = 0;
  v7 = (_QWORD *)((char *)this + 88);
  v12 = DVRCreateDVRFileSink(a2, hKey, 0, 0, 0, (char *)this + 88);
  if ( v12 >= 0 )
  {
    if ( *((_QWORD *)this + 4) )
    {
      v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v7)(*v7, &IID_IDVRFileSink2, &v20);
      if ( v12 < 0 )
        goto LABEL_21;
      v9 = operator new(0xA8u);
      if ( v9 )
      {
        v14 = &CPVRStreamProf::`vftable';
        v15 = v18[2];
        v16 = v18[3];
        v17 = v18[4];
        v10 = (CPVRAsyncWriterCOM *)CPVRAsyncWriterCOM::CPVRAsyncWriterCOM(
                                      v9,
                                      *((unsigned int *)this + 10),
                                      *((unsigned int *)this + 11),
                                      *((unsigned int *)this + 12),
                                      *((_DWORD *)this + 13),
                                      *((_QWORD *)this + 4),
                                      a3,
                                      0,
                                      0,
                                      0,
                                      0,
                                      &v14,
                                      &v13);
        v6 = v13;
      }
      else
      {
        v10 = 0;
      }
      if ( !v10 )
      {
        v12 = -2147024882;
        goto LABEL_21;
      }
      if ( v6 )
      {
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        v12 = v6;
        CPVRAsyncWriterCOM::`scalar deleting destructor'(v10, v8);
        goto LABEL_21;
      }
      (*(void (__fastcall **)(CPVRAsyncWriterCOM *))(*(_QWORD *)v10 + 8LL))(v10);
      v12 = (*(__int64 (__fastcall **)(__int64, CPVRAsyncWriterCOM *))(*(_QWORD *)v20 + 80LL))(v20, v10);
      (*(void (__fastcall **)(CPVRAsyncWriterCOM *))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v12 < 0 )
        goto LABEL_21;
    }
    v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v7)(*v7, &IID_IWMRegisterCallback, &v21);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v21 + 24LL))(
              v21,
              -(__int64)(this != 0) & ((unsigned __int64)this + 8),
              0);
      if ( v12 >= 0 )
      {
        v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v7)(*v7, &IID_IWMWriterFileSink, (char *)this + 104);
        if ( v12 >= 0 )
        {
          v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v7)(*v7, &IID_IWMWriterSink, (char *)this + 96);
          if ( v12 >= 0 )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 24LL))(*v7, 0);
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v7 + 32LL))(
              *v7,
              *((unsigned int *)this + 14),
              *((unsigned int *)this + 15));
          }
        }
      }
    }
  }
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006d028  mov     r11, rsp
0x18006d02b  mov     [r11+20h], rbx
0x18006d02f  push    rsi
0x18006d030  push    rdi
0x18006d031  push    r12
0x18006d033  push    r14
0x18006d035  push    r15
0x18006d037  sub     rsp, 0D0h
0x18006d03e  mov     rax, cs:__security_cookie
0x18006d045  xor     rax, rsp
0x18006d048  mov     [rsp+0F8h+var_38], rax
0x18006d050  mov     r12, r8
0x18006d053  mov     r14, rdx
0x18006d056  mov     rsi, rcx
0x18006d059  xor     ebx, ebx
0x18006d05b  mov     [rsp+0F8h+var_88], ebx
0x18006d05f  lea     rcx, [r11-68h]; this
0x18006d063  call    ??0CPVREmptyProf@@QEAA@XZ; CPVREmptyProf::CPVREmptyProf(void)
0x18006d068  mov     [rsp+0F8h+hKey], rbx
0x18006d070  mov     [rsp+0F8h+var_48], rbx
0x18006d078  mov     [rsp+0F8h+var_40], rbx
0x18006d080  mov     [rsp+0F8h+lpdwDisposition], rbx; lpdwDisposition
0x18006d085  lea     rax, [rsp+0F8h+hKey]
0x18006d08d  mov     [rsp+0F8h+phkResult], rax; phkResult
0x18006d092  mov     [rsp+0F8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18006d097  mov     [rsp+0F8h+samDesired], 2001Fh; samDesired
0x18006d09f  mov     [rsp+0F8h+dwOptions], ebx; dwOptions
0x18006d0a3  xor     r9d, r9d; lpClass
0x18006d0a6  xor     r8d, r8d; Reserved
0x18006d0a9  lea     rdx, aIoWriter; "IO\\Writer"
0x18006d0b0  mov     rcx, r14; hKey
0x18006d0b3  call    cs:__imp_RegCreateKeyExW
0x18006d0b9  mov     edi, eax
0x18006d0bb  mov     [rsp+0F8h+var_84], eax
0x18006d0bf  test    eax, eax
0x18006d0c1  jz      short loc_18006D0CB
0x18006d0c3  mov     [rsp+0F8h+hKey], rbx
0x18006d0cb  lea     r15, [rsi+58h]
0x18006d0cf  mov     qword ptr [rsp+0F8h+samDesired], r15
0x18006d0d4  mov     [rsp+0F8h+dwOptions], ebx
0x18006d0d8  xor     r9d, r9d
0x18006d0db  xor     r8d, r8d
0x18006d0de  mov     rdx, [rsp+0F8h+hKey]
0x18006d0e6  mov     rcx, r14
0x18006d0e9  call    cs:__imp_DVRCreateDVRFileSink
0x18006d0ef  mov     [rsp+0F8h+var_88], eax
0x18006d0f3  mov     eax, [rsp+0F8h+var_88]
0x18006d0f7  test    eax, eax
0x18006d0f9  js      loc_18006D329
0x18006d0ff  cmp     [rsi+20h], rbx
0x18006d103  jz      loc_18006D254
0x18006d109  mov     rcx, [r15]
0x18006d10c  mov     rax, [rcx]
0x18006d10f  lea     r8, [rsp+0F8h+var_48]
0x18006d117  lea     rdx, IID_IDVRFileSink2
0x18006d11e  mov     rax, [rax]
0x18006d121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d126  mov     [rsp+0F8h+var_88], eax
0x18006d12a  mov     eax, [rsp+0F8h+var_88]
0x18006d12e  test    eax, eax
0x18006d130  js      loc_18006D329
0x18006d136  mov     ecx, 0A8h; Size
0x18006d13b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d140  mov     r10, rax
0x18006d143  test    rax, rax
0x18006d146  jz      loc_18006D1DA
0x18006d14c  lea     rax, ??_7CPVRStreamProf@@6B@; const CPVRStreamProf::`vftable'
0x18006d153  mov     [rsp+0F8h+var_80], rax
0x18006d158  mov     ecx, [rsp+0F8h+var_60]
0x18006d15f  mov     [rsp+0F8h+var_78], ecx
0x18006d166  mov     ecx, [rsp+0F8h+var_5C]
0x18006d16d  mov     [rsp+0F8h+var_74], ecx
0x18006d174  mov     ecx, [rsp+0F8h+var_58]
0x18006d17b  mov     [rsp+0F8h+var_70], ecx
0x18006d182  lea     rax, [rsp+0F8h+var_84]
0x18006d187  mov     [rsp+0F8h+var_98], rax
0x18006d18c  lea     rax, [rsp+0F8h+var_80]
0x18006d191  mov     [rsp+0F8h+var_A0], rax
0x18006d196  mov     [rsp+0F8h+var_A8], rbx
0x18006d19b  mov     [rsp+0F8h+var_B0], rbx
0x18006d1a0  mov     [rsp+0F8h+lpdwDisposition], rbx
0x18006d1a5  mov     dword ptr [rsp+0F8h+phkResult], ebx
0x18006d1a9  mov     [rsp+0F8h+lpSecurityAttributes], r12
0x18006d1ae  mov     rax, [rsi+20h]
0x18006d1b2  mov     qword ptr [rsp+0F8h+samDesired], rax
0x18006d1b7  mov     eax, [rsi+34h]
0x18006d1ba  mov     [rsp+0F8h+dwOptions], eax
0x18006d1be  mov     r9d, [rsi+30h]
0x18006d1c2  mov     r8d, [rsi+2Ch]
0x18006d1c6  mov     edx, [rsi+28h]
0x18006d1c9  mov     rcx, r10
0x18006d1cc  call    ??0CPVRAsyncWriterCOM@@QEAA@KKKKPEAVCAsyncIo@@PEAVCPVRIOCounters@@KPEAPEAXP6AXPEAXK_J4@Z3VCPVRStreamProf@@PEAK@Z; CPVRAsyncWriterCOM::CPVRAsyncWriterCOM(ulong,ulong,ulong,ulong,CAsyncIo *,CPVRIOCounters *,ulong,void * *,void (*)(void *,ulong,__int64,__int64),void *,CPVRStreamProf,ulong *)
0x18006d1d1  mov     r14, rax
0x18006d1d4  mov     edi, [rsp+0F8h+var_84]
0x18006d1d8  jmp     short loc_18006D1DD
0x18006d1da  mov     r14, rbx
0x18006d1dd  test    r14, r14
0x18006d1e0  jnz     short loc_18006D1EF
0x18006d1e2  mov     [rsp+0F8h+var_88], 8007000Eh
0x18006d1ea  jmp     loc_18006D329
0x18006d1ef  test    edi, edi
0x18006d1f1  jz      short loc_18006D20F
0x18006d1f3  jle     short loc_18006D1FE
0x18006d1f5  movzx   edi, di
0x18006d1f8  or      edi, 80070000h
0x18006d1fe  mov     [rsp+0F8h+var_88], edi
0x18006d202  mov     rcx, r14; this
0x18006d205  call    ??_GCPVRAsyncWriterCOM@@QEAAPEAXI@Z; CPVRAsyncWriterCOM::`scalar deleting destructor'(uint)
0x18006d20a  jmp     loc_18006D329
0x18006d20f  mov     rax, [r14]
0x18006d212  mov     rcx, r14
0x18006d215  mov     rax, [rax+8]
0x18006d219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d21e  mov     rcx, [rsp+0F8h+var_48]
0x18006d226  mov     rax, [rcx]
0x18006d229  mov     rdx, r14
0x18006d22c  mov     rax, [rax+50h]
0x18006d230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d235  mov     [rsp+0F8h+var_88], eax
0x18006d239  mov     rax, [r14]
0x18006d23c  mov     rcx, r14
0x18006d23f  mov     rax, [rax+10h]
0x18006d243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d248  mov     eax, [rsp+0F8h+var_88]
0x18006d24c  test    eax, eax
0x18006d24e  js      loc_18006D329
0x18006d254  mov     rcx, [r15]
0x18006d257  mov     rax, [rcx]
0x18006d25a  lea     r8, [rsp+0F8h+var_40]
0x18006d262  lea     rdx, IID_IWMRegisterCallback
0x18006d269  mov     rax, [rax]
0x18006d26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d271  mov     [rsp+0F8h+var_88], eax
0x18006d275  mov     eax, [rsp+0F8h+var_88]
0x18006d279  test    eax, eax
0x18006d27b  js      loc_18006D329
0x18006d281  mov     rcx, [rsp+0F8h+var_40]
0x18006d289  mov     r10, [rcx]
0x18006d28c  mov     rax, rsi
0x18006d28f  lea     rdx, [rsi+8]
0x18006d293  neg     rax
0x18006d296  sbb     r9, r9
0x18006d299  and     rdx, r9
0x18006d29c  xor     r8d, r8d
0x18006d29f  mov     rax, [r10+18h]
0x18006d2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2a8  mov     [rsp+0F8h+var_88], eax
0x18006d2ac  mov     eax, [rsp+0F8h+var_88]
0x18006d2b0  test    eax, eax
0x18006d2b2  js      short loc_18006D329
0x18006d2b4  mov     rcx, [r15]
0x18006d2b7  mov     rax, [rcx]
0x18006d2ba  lea     r8, [rsi+68h]
0x18006d2be  lea     rdx, IID_IWMWriterFileSink
0x18006d2c5  mov     rax, [rax]
0x18006d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2cd  mov     [rsp+0F8h+var_88], eax
0x18006d2d1  mov     eax, [rsp+0F8h+var_88]
0x18006d2d5  test    eax, eax
0x18006d2d7  js      short loc_18006D329
0x18006d2d9  mov     rcx, [r15]
0x18006d2dc  mov     rax, [rcx]
0x18006d2df  lea     r8, [rsi+60h]
0x18006d2e3  lea     rdx, IID_IWMWriterSink
0x18006d2ea  mov     rax, [rax]
0x18006d2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2f2  mov     [rsp+0F8h+var_88], eax
0x18006d2f6  mov     eax, [rsp+0F8h+var_88]
0x18006d2fa  test    eax, eax
0x18006d2fc  js      short loc_18006D329
0x18006d2fe  mov     rcx, [r15]
0x18006d301  mov     rax, [rcx]
0x18006d304  xor     edx, edx
0x18006d306  mov     rax, [rax+18h]
0x18006d30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d30f  mov     rcx, [r15]
0x18006d312  mov     rax, [rcx]
0x18006d315  mov     r8d, [rsi+3Ch]
0x18006d319  mov     edx, [rsi+38h]
0x18006d31c  mov     rax, [rax+20h]
0x18006d320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d325  jmp     short loc_18006D329
0x18006d327  xor     ebx, ebx
0x18006d329  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18006d331  test    rcx, rcx
0x18006d334  jz      short loc_18006D33C
0x18006d336  call    cs:__imp_RegCloseKey
0x18006d33c  mov     rcx, [rsp+0F8h+var_48]
0x18006d344  test    rcx, rcx
0x18006d347  jz      short loc_18006D35D
0x18006d349  mov     rax, [rcx]
0x18006d34c  mov     rax, [rax+10h]
0x18006d350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d355  mov     [rsp+0F8h+var_48], rbx
0x18006d35d  mov     rcx, [rsp+0F8h+var_40]
0x18006d365  test    rcx, rcx
0x18006d368  jz      short loc_18006D376
0x18006d36a  mov     rax, [rcx]
0x18006d36d  mov     rax, [rax+10h]
0x18006d371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d376  mov     eax, [rsp+0F8h+var_88]
0x18006d37a  mov     rcx, [rsp+0F8h+var_38]
0x18006d382  xor     rcx, rsp; StackCookie
0x18006d385  call    __security_check_cookie
0x18006d38a  mov     rbx, [rsp+0F8h+arg_18]
0x18006d392  add     rsp, 0D0h
0x18006d399  pop     r15
0x18006d39b  pop     r14
0x18006d39d  pop     r12
0x18006d39f  pop     rdi
0x18006d3a0  pop     rsi
0x18006d3a1  retn
0x1800b3a34  push    rbp
0x1800b3a36  sub     rsp, 70h
0x1800b3a3a  mov     rbp, rdx
0x1800b3a3d  lea     rdx, [rbp+70h]; int *
0x1800b3a41  call    ?SBE_DelayLoadDllExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@PEAJ@Z; SBE_DelayLoadDllExceptionFilter(_EXCEPTION_POINTERS *,long *)
0x1800b3a46  nop
0x1800b3a47  add     rsp, 70h
0x1800b3a4b  pop     rbp
0x1800b3a4c  retn
```
