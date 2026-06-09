# LoadConfig(void)

- ea: `0x140001404`
- end: `0x14000166d`
- name: `?LoadConfig@@YAJXZ`
- size: `617`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140022078`

## callees

- `0x140001404`
- `0x14000f900`
- `0x14000f9e0`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1400015f7`
- `ntoskrnl!KeInitializeMutex` at `0x1400015f7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400014ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400014ec`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400014fd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400014fd`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140001521`

## string_xrefs

- `0x14000148c`: `RtlQueryRegistryValuesEx`
- `0x1400014a4`: `TrackingConfig`
- `0x14000147e`: `LogConfig`

## pseudocode

```c
__int64 LoadConfig(void)
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, const WCHAR *, _QWORD *); // rax
  int v1; // eax
  __int64 v2; // rcx
  unsigned int v3; // ebx
  char v5; // [rsp+30h] [rbp-D0h] BYREF
  int v6; // [rsp+31h] [rbp-CFh]
  __int16 v7; // [rsp+35h] [rbp-CBh]
  char v8; // [rsp+37h] [rbp-C9h]
  __int128 v9; // [rsp+38h] [rbp-C8h]
  char v10; // [rsp+48h] [rbp-B8h] BYREF
  int v11; // [rsp+49h] [rbp-B7h]
  __int16 v12; // [rsp+4Dh] [rbp-B3h]
  char v13; // [rsp+4Fh] [rbp-B1h]
  __int128 v14; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v16[22]; // [rsp+70h] [rbp-90h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  memset(v16, 0, 0xA8u);
  v5 = 1;
  LODWORD(v16[1]) = 256;
  LODWORD(v16[4]) = 3;
  LODWORD(v16[8]) = 256;
  v16[2] = L"LogConfig";
  LODWORD(v16[11]) = 3;
  v16[3] = &v5;
  v16[0] = ConfigQueryRoutine;
  v16[9] = L"TrackingConfig";
  v16[5] = 0;
  v16[10] = &v10;
  LODWORD(v16[6]) = 0;
  v16[7] = ConfigQueryRoutine;
  v10 = 2;
  v16[12] = 0;
  LODWORD(v16[13]) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const WCHAR *, _QWORD *))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const WCHAR *, _QWORD *))RtlQueryRegistryValues;
  v1 = SystemRoutineAddress(2, L"WinSetupMon", v16);
  v2 = v9;
  v3 = v1;
  if ( v1 >= 0 )
  {
    if ( !(_QWORD)v9 )
    {
LABEL_7:
      v3 = -1073741637;
      goto LABEL_8;
    }
    if ( !(**(__int64 (__fastcall ***)(_QWORD))v9)(v9) )
    {
      v2 = v9;
      goto LABEL_7;
    }
    KeInitializeMutex(&Mutex, 0);
    qword_140019348 = v9;
    v6 = 0;
    v5 = 0;
    qword_140019358 = *((_QWORD *)&v14 + 1);
    v7 = 0;
    v8 = 0;
    v11 = 0;
    v12 = 0;
    v13 = 0;
    P = 0;
    v2 = 0;
    v10 = 0;
    v9 = 0;
    v14 = 0;
    byte_140019370 = 1;
  }
LABEL_8:
  if ( *((_QWORD *)&v14 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v14 + 1) + 8LL))(*((_QWORD *)&v14 + 1));
    v2 = v9;
  }
  if ( (_QWORD)v14 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 8LL))(v14);
    v2 = v9;
  }
  if ( *((_QWORD *)&v9 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v9 + 1) + 8LL))(*((_QWORD *)&v9 + 1));
    v2 = v9;
  }
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  return v3;
}

```

## disassembly

```asm
0x140001404  mov     [rsp-8+arg_0], rbx
0x140001409  push    rbp
0x14000140a  lea     rbp, [rsp-30h]
0x14000140f  sub     rsp, 130h
0x140001416  mov     rax, cs:__security_cookie
0x14000141d  xor     rax, rsp
0x140001420  mov     [rbp+30h+var_10], rax
0x140001424  xor     eax, eax
0x140001426  lea     rcx, [rsp+130h+var_C0]; void *
0x14000142b  xorps   xmm0, xmm0
0x14000142e  mov     [rsp+130h+var_FF], eax
0x140001432  xor     edx, edx; Val
0x140001434  mov     [rsp+130h+var_FB], ax
0x140001439  mov     r8d, 0A8h; Size
0x14000143f  mov     [rsp+130h+var_F9], al
0x140001443  movdqu  [rsp+130h+var_F8], xmm0
0x140001449  mov     [rsp+130h+var_E7], eax
0x14000144d  mov     [rsp+130h+var_E3], ax
0x140001452  mov     [rsp+130h+var_E1], al
0x140001456  movdqu  [rsp+130h+var_E0], xmm0
0x14000145c  call    memset
0x140001461  mov     edx, 100h
0x140001466  mov     [rsp+130h+var_100], 1
0x14000146b  mov     ecx, 3
0x140001470  mov     [rsp+130h+var_B8], edx
0x140001474  lea     r8, ?ConfigQueryRoutine@@YAJPEAGKPEAXK11@Z; ConfigQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x14000147b  mov     [rbp+30h+var_A0], ecx
0x14000147e  lea     rax, ValueName; "LogConfig"
0x140001485  mov     [rbp+30h+var_80], edx
0x140001488  mov     [rbp+30h+var_B0], rax
0x14000148c  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140001493  lea     rax, [rsp+130h+var_100]
0x140001498  mov     [rbp+30h+var_68], ecx
0x14000149b  mov     [rbp+30h+var_A8], rax
0x14000149f  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1400014a4  lea     rax, aTrackingconfig; "TrackingConfig"
0x1400014ab  mov     [rsp+130h+var_C0], r8
0x1400014b0  mov     [rbp+30h+var_78], rax
0x1400014b4  xorps   xmm0, xmm0
0x1400014b7  lea     rax, [rsp+130h+var_E8]
0x1400014bc  mov     [rbp+30h+var_98], 0
0x1400014c4  mov     [rbp+30h+var_70], rax
0x1400014c8  mov     [rbp+30h+var_90], 0
0x1400014cf  mov     [rbp+30h+var_88], r8
0x1400014d3  mov     [rsp+130h+var_E8], 2
0x1400014d8  mov     [rbp+30h+var_60], 0
0x1400014e0  mov     [rbp+30h+var_58], 0
0x1400014e7  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1400014ec  call    cs:__imp_RtlInitUnicodeString
0x1400014f3  nop     dword ptr [rax+rax+00h]
0x1400014f8  lea     rcx, [rsp+130h+DestinationString]; SystemRoutineName
0x1400014fd  call    cs:__imp_MmGetSystemRoutineAddress
0x140001504  nop     dword ptr [rax+rax+00h]
0x140001509  lea     r8, [rsp+130h+var_C0]
0x14000150e  mov     [rsp+130h+var_110], 0
0x140001517  test    rax, rax
0x14000151a  lea     rdx, Path; "WinSetupMon"
0x140001521  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140001529  xor     r9d, r9d
0x14000152c  lea     ecx, [r9+2]
0x140001530  call    _guard_dispatch_icall
0x140001535  mov     rcx, qword ptr [rsp+130h+var_F8]
0x14000153a  mov     ebx, eax
0x14000153c  test    eax, eax
0x14000153e  js      short loc_140001563
0x140001540  test    rcx, rcx
0x140001543  jz      short loc_14000155E
0x140001545  mov     rdx, [rcx]
0x140001548  mov     rax, [rdx]
0x14000154b  call    _guard_dispatch_icall
0x140001550  test    rax, rax
0x140001553  jnz     loc_1400015EE
0x140001559  mov     rcx, qword ptr [rsp+130h+var_F8]
0x14000155e  mov     ebx, 0C00000BBh
0x140001563  mov     rdx, qword ptr [rsp+130h+var_E0+8]
0x140001568  test    rdx, rdx
0x14000156b  jz      short loc_140001581
0x14000156d  mov     rax, [rdx]
0x140001570  mov     rcx, rdx
0x140001573  mov     rax, [rax+8]
0x140001577  call    _guard_dispatch_icall
0x14000157c  mov     rcx, qword ptr [rsp+130h+var_F8]
0x140001581  mov     rdx, qword ptr [rsp+130h+var_E0]
0x140001586  test    rdx, rdx
0x140001589  jz      short loc_14000159F
0x14000158b  mov     rax, [rdx]
0x14000158e  mov     rcx, rdx
0x140001591  mov     rax, [rax+8]
0x140001595  call    _guard_dispatch_icall
0x14000159a  mov     rcx, qword ptr [rsp+130h+var_F8]
0x14000159f  mov     rdx, qword ptr [rsp+130h+var_F8+8]
0x1400015a4  test    rdx, rdx
0x1400015a7  jz      short loc_1400015BD
0x1400015a9  mov     rax, [rdx]
0x1400015ac  mov     rcx, rdx
0x1400015af  mov     rax, [rax+8]
0x1400015b3  call    _guard_dispatch_icall
0x1400015b8  mov     rcx, qword ptr [rsp+130h+var_F8]
0x1400015bd  test    rcx, rcx
0x1400015c0  jz      short loc_1400015CE
0x1400015c2  mov     rax, [rcx]
0x1400015c5  mov     rax, [rax+8]
0x1400015c9  call    _guard_dispatch_icall
0x1400015ce  mov     eax, ebx
0x1400015d0  mov     rcx, [rbp+30h+var_10]
0x1400015d4  xor     rcx, rsp; StackCookie
0x1400015d7  call    __security_check_cookie
0x1400015dc  mov     rbx, [rsp+130h+arg_0]
0x1400015e4  add     rsp, 130h
0x1400015eb  pop     rbp
0x1400015ec  retn
0x1400015ee  xor     edx, edx; Level
0x1400015f0  lea     rcx, Mutex; Mutex
0x1400015f7  call    cs:__imp_KeInitializeMutex
0x1400015fe  nop     dword ptr [rax+rax+00h]
0x140001603  mov     rax, qword ptr [rsp+130h+var_F8]
0x140001608  xor     ecx, ecx
0x14000160a  mov     cs:qword_140019348, rax
0x140001611  xorps   xmm1, xmm1
0x140001614  xor     al, al
0x140001616  mov     [rsp+130h+var_FF], ecx
0x14000161a  mov     [rsp+130h+var_100], al
0x14000161e  xorps   xmm0, xmm0
0x140001621  mov     rax, qword ptr [rsp+130h+var_E0+8]
0x140001626  mov     cs:qword_140019358, rax
0x14000162d  xor     al, al
0x14000162f  mov     [rsp+130h+var_FB], cx
0x140001634  mov     [rsp+130h+var_F9], cl
0x140001638  mov     [rsp+130h+var_E7], ecx
0x14000163c  mov     [rsp+130h+var_E3], cx
0x140001641  mov     [rsp+130h+var_E1], cl
0x140001645  mov     cs:P, rcx
0x14000164c  movq    rcx, xmm1
0x140001651  mov     [rsp+130h+var_E8], al
0x140001655  movdqu  [rsp+130h+var_F8], xmm1
0x14000165b  movdqu  [rsp+130h+var_E0], xmm0
0x140001661  mov     cs:byte_140019370, 1
0x140001668  jmp     loc_140001563
```
