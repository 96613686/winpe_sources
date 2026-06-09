# SNI_Spn::SpnInit(void)

- ea: `0x383891ef0`
- end: `0x383892167`
- name: `?SpnInit@SNI_Spn@@SAKXZ`
- size: `631`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x383891c80`

## callees

- `0x3838914c0`
- `0x383891ef0`
- `0x383892180`
- `0x3838bdad0`
- `0x38391ac20`
- `0x38391ac40`
- `0x38391ae80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383906a8c`
- `KERNEL32!GetLastError` at `0x383906a8c`
- `KERNEL32!SetLastError` at `0x383906a86`
- `KERNEL32!SetLastError` at `0x383906a86`
- `KERNEL32!GetProcAddress` at `0x383891f46`
- `KERNEL32!GetProcAddress` at `0x383891f6a`
- `KERNEL32!GetProcAddress` at `0x383891f8e`
- `KERNEL32!GetProcAddress` at `0x383891fb2`
- `KERNEL32!GetProcAddress` at `0x383891fd6`
- `KERNEL32!GetProcAddress` at `0x383891ffa`
- `KERNEL32!GetProcAddress` at `0x38389201e`
- `KERNEL32!GetProcAddress` at `0x38389205a`
- `KERNEL32!GetProcAddress` at `0x38389207e`
- `KERNEL32!GetProcAddress` at `0x3838920ba`
- `KERNEL32!GetProcAddress` at `0x3838920de`
- `KERNEL32!GetProcAddress` at `0x383891f46`
- `KERNEL32!GetProcAddress` at `0x383891f6a`
- `KERNEL32!GetProcAddress` at `0x383891f8e`
- `KERNEL32!GetProcAddress` at `0x383891fb2`
- `KERNEL32!GetProcAddress` at `0x383891fd6`
- `KERNEL32!GetProcAddress` at `0x383891ffa`
- `KERNEL32!GetProcAddress` at `0x38389201e`
- `KERNEL32!GetProcAddress` at `0x38389205a`
- `KERNEL32!GetProcAddress` at `0x38389207e`
- `KERNEL32!GetProcAddress` at `0x3838920ba`
- `KERNEL32!GetProcAddress` at `0x3838920de`

## string_xrefs

- `0x383892094`: `secur32.dll`
- `0x383892034`: `netapi32.dll`
- `0x383891f20`: `ntdsapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SNI_Spn::SpnInit(void)
{
  HMODULE v0; // rax
  HMODULE v1; // rax
  HMODULE v2; // rax
  __int64 v3; // rax
  DWORD v4; // eax
  DWORD v6; // ecx
  DWORD LastError; // ebx
  int v8; // [rsp+20h] [rbp-28h]

  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48DB8[0] && bidID != -1 )
  {
    v8 = (int)off_383B48DB8[0];
    off_383B15048();
  }
  v0 = SNILoadSystemLibA("ntdsapi.dll");
  ghSpnLib = v0;
  if ( v0 )
  {
    gDsFunc = GetProcAddress(v0, DsFunctionNames);
    if ( gDsFunc )
    {
      qword_383B23838 = (__int64)GetProcAddress(ghSpnLib, lpProcName);
      if ( qword_383B23838 )
      {
        qword_383B23840 = (__int64)GetProcAddress(ghSpnLib, off_383B23910);
        if ( qword_383B23840 )
        {
          qword_383B23848 = (__int64)GetProcAddress(ghSpnLib, off_383B23918);
          if ( qword_383B23848 )
          {
            qword_383B23850 = (__int64)GetProcAddress(ghSpnLib, off_383B23920);
            if ( qword_383B23850 )
            {
              qword_383B23858 = (__int64)GetProcAddress(ghSpnLib, off_383B23928);
              if ( qword_383B23858 )
              {
                qword_383B23860 = (__int64)GetProcAddress(ghSpnLib, off_383B23930);
                if ( qword_383B23860 )
                {
                  v1 = SNILoadSystemLibA("netapi32.dll");
                  ghNetApiLib = v1;
                  if ( v1 )
                  {
                    qword_383B23868 = (__int64)GetProcAddress(v1, off_383B23938);
                    if ( qword_383B23868 )
                    {
                      qword_383B23870 = (__int64)GetProcAddress(ghNetApiLib, "NetApiBufferFree");
                      if ( qword_383B23870 )
                      {
                        v2 = SNILoadSystemLibA("secur32.dll");
                        ghSecur = v2;
                        if ( v2 )
                        {
                          qword_383B23878 = (__int64)GetProcAddress(v2, off_383B23940);
                          if ( qword_383B23878 )
                          {
                            qword_383B23880 = (__int64)GetProcAddress(ghSecur, off_383B23948);
                            if ( qword_383B23880 )
                            {
                              v3 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(
                                     gpmo,
                                     24);
                              if ( v3 )
                              {
                                *(_QWORD *)v3 = 0;
                                *(_QWORD *)(v3 + 8) = 0;
                                *(_DWORD *)(v3 + 16) = 0;
                              }
                              else
                              {
                                v3 = 0;
                              }
                              SNI_Spn::m_peventSpnRegistrationCompleted = (SNIAutoEvent *)v3;
                              if ( v3 )
                              {
                                v4 = SNIAutoEvent::FInit((SNIAutoEvent *)v3);
                                if ( !v4 )
                                {
                                  if ( (bidGblFlags & 0x20002) == 0x20002 )
                                  {
                                    if ( off_383B48048[0] )
                                      bidTraceA(off_383B459C8[0], 165888, off_383B48048[0], 0, v8);
                                  }
                                  return 0;
                                }
                                v6 = v4;
                              }
                              else
                              {
                                v6 = 14;
                              }
                              SetLastError(v6);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  LastError = GetLastError();
  SNI_Spn::SpnTerminate();
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48040[0] )
    bidTraceA(off_383B459C0[0], 176128, off_383B48040[0], LastError, v8);
  return LastError;
}

```

## disassembly

```asm
0x383891ef0  push    rbx
0x383891ef2  sub     rsp, 40h
0x383891ef6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x383891eff  mov     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383891f08  mov     eax, cs:_bidGblFlags
0x383891f0e  and     eax, 20004h
0x383891f13  xor     ebx, ebx
0x383891f15  cmp     eax, 20004h
0x383891f1a  jz      loc_3839069C4
0x383891f20  lea     rcx, aNtdsapiDll; "ntdsapi.dll"
0x383891f27  call    SNILoadSystemLibA
0x383891f2c  mov     cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghSpnLib
0x383891f33  test    rax, rax
0x383891f36  jz      loc_383906A8C
0x383891f3c  mov     rdx, cs:?DsFunctionNames@@3PAPEBDA; lpProcName
0x383891f43  mov     rcx, rax; hModule
0x383891f46  call    cs:__imp_GetProcAddress
0x383891f4c  mov     cs:?gDsFunc@@3U_DsFunctionTable@@A, rax; _DsFunctionTable gDsFunc
0x383891f53  test    rax, rax
0x383891f56  jz      loc_383906A8C
0x383891f5c  mov     rdx, cs:lpProcName; lpProcName
0x383891f63  mov     rcx, cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA; hModule
0x383891f6a  call    cs:__imp_GetProcAddress
0x383891f70  mov     cs:qword_383B23838, rax
0x383891f77  test    rax, rax
0x383891f7a  jz      loc_383906A8C
0x383891f80  mov     rdx, cs:off_383B23910; lpProcName
0x383891f87  mov     rcx, cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA; hModule
0x383891f8e  call    cs:__imp_GetProcAddress
0x383891f94  mov     cs:qword_383B23840, rax
0x383891f9b  test    rax, rax
0x383891f9e  jz      loc_383906A8C
0x383891fa4  mov     rdx, cs:off_383B23918; lpProcName
0x383891fab  mov     rcx, cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA; hModule
0x383891fb2  call    cs:__imp_GetProcAddress
0x383891fb8  mov     cs:qword_383B23848, rax
0x383891fbf  test    rax, rax
0x383891fc2  jz      loc_383906A8C
0x383891fc8  mov     rdx, cs:off_383B23920; lpProcName
0x383891fcf  mov     rcx, cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA; hModule
0x383891fd6  call    cs:__imp_GetProcAddress
0x383891fdc  mov     cs:qword_383B23850, rax
0x383891fe3  test    rax, rax
0x383891fe6  jz      loc_383906A8C
0x383891fec  mov     rdx, cs:off_383B23928; lpProcName
0x383891ff3  mov     rcx, cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA; hModule
0x383891ffa  call    cs:__imp_GetProcAddress
0x383892000  mov     cs:qword_383B23858, rax
0x383892007  test    rax, rax
0x38389200a  jz      loc_383906A8C
0x383892010  mov     rdx, cs:off_383B23930; lpProcName
0x383892017  mov     rcx, cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA; hModule
0x38389201e  call    cs:__imp_GetProcAddress
0x383892024  mov     cs:qword_383B23860, rax
0x38389202b  test    rax, rax
0x38389202e  jz      loc_383906A8C
0x383892034  lea     rcx, aNetapi32Dll_0; "netapi32.dll"
0x38389203b  call    SNILoadSystemLibA
0x383892040  mov     cs:?ghNetApiLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghNetApiLib
0x383892047  test    rax, rax
0x38389204a  jz      loc_383906A8C
0x383892050  mov     rdx, cs:off_383B23938; lpProcName
0x383892057  mov     rcx, rax; hModule
0x38389205a  call    cs:__imp_GetProcAddress
0x383892060  mov     cs:qword_383B23868, rax
0x383892067  test    rax, rax
0x38389206a  jz      loc_383906A8C
0x383892070  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x383892077  mov     rcx, cs:?ghNetApiLib@@3PEAUHINSTANCE__@@EA; hModule
0x38389207e  call    cs:__imp_GetProcAddress
0x383892084  mov     cs:qword_383B23870, rax
0x38389208b  test    rax, rax
0x38389208e  jz      loc_383906A8C
0x383892094  lea     rcx, aSecur32Dll; "secur32.dll"
0x38389209b  call    SNILoadSystemLibA
0x3838920a0  mov     cs:?ghSecur@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghSecur
0x3838920a7  test    rax, rax
0x3838920aa  jz      loc_383906A8C
0x3838920b0  mov     rdx, cs:off_383B23940; lpProcName
0x3838920b7  mov     rcx, rax; hModule
0x3838920ba  call    cs:__imp_GetProcAddress
0x3838920c0  mov     cs:qword_383B23878, rax
0x3838920c7  test    rax, rax
0x3838920ca  jz      loc_383906A8C
0x3838920d0  mov     rdx, cs:off_383B23948; lpProcName
0x3838920d7  mov     rcx, cs:?ghSecur@@3PEAUHINSTANCE__@@EA; hModule
0x3838920de  call    cs:__imp_GetProcAddress
0x3838920e4  mov     cs:qword_383B23880, rax
0x3838920eb  test    rax, rax
0x3838920ee  jz      loc_383906A8C
0x3838920f4  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x3838920fb  mov     rax, [rcx]
0x3838920fe  mov     edx, 18h
0x383892103  call    qword ptr [rax+58h]
0x383892106  test    rax, rax
0x383892109  jz      loc_383906A10
0x38389210f  mov     [rax], rbx
0x383892112  mov     [rax+8], rbx
0x383892116  mov     [rax+10h], ebx
0x383892119  jmp     short $+2
0x38389211b  mov     cs:?m_peventSpnRegistrationCompleted@SNI_Spn@@0PEAVSNIAutoEvent@@EA, rax; SNIAutoEvent * SNI_Spn::m_peventSpnRegistrationCompleted
0x383892122  test    rax, rax
0x383892125  jz      loc_383906A18
0x38389212b  mov     rcx, rax; this
0x38389212e  call    ?FInit@SNIAutoEvent@@QEAAKXZ; SNIAutoEvent::FInit(void)
0x383892133  test    eax, eax
0x383892135  jnz     loc_383906A1D
0x38389213b  mov     eax, cs:_bidGblFlags
0x383892141  and     eax, 20002h
0x383892146  cmp     eax, 20002h
0x38389214b  jz      loc_383906A21
0x383892151  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383892157  jnz     loc_383906A52
0x38389215d  xor     eax, eax
0x38389215f  jmp     short $+2
0x383892161  add     rsp, 40h
0x383892165  pop     rbx
0x383892166  retn
0x3839069c4  mov     rax, cs:off_383B48DB8; "<SNI_Spn::SpnInit|API|SNI> \n"
0x3839069cb  test    rax, rax
0x3839069ce  jz      loc_383891F20
0x3839069d4  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3839069dc  jz      loc_383891F20
0x3839069e2  mov     [rsp+48h+var_20], rbx
0x3839069e7  mov     rax, cs:off_383B48DB8; "<SNI_Spn::SpnInit|API|SNI> \n"
0x3839069ee  mov     [rsp+48h+var_28], rax
0x3839069f3  lea     r9, [rsp+48h+arg_0]
0x3839069f8  xor     r8d, r8d
0x3839069fb  xor     edx, edx
0x3839069fd  mov     rcx, cs:_bidID
0x383906a04  call    cs:off_383B15048
0x383906a0a  nop
0x383906a0b  jmp     loc_383891F20
0x383906a10  mov     rax, rbx
0x383906a13  jmp     loc_38389211B
0x383906a18  lea     ecx, [rax+0Eh]; dwErrCode
0x383906a1b  jmp     short loc_383906A86
0x383906a1d  mov     ecx, eax
0x383906a1f  jmp     short loc_383906A86
0x383906a21  mov     rax, cs:off_383B48048; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x383906a28  test    rax, rax
0x383906a2b  jz      loc_383892151
0x383906a31  xor     r9d, r9d
0x383906a34  mov     r8, cs:off_383B48048; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x383906a3b  mov     edx, 28800h
0x383906a40  mov     rcx, cs:off_383B459C8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383906a47  call    _bidTraceA
0x383906a4c  nop
0x383906a4d  jmp     loc_383892151
0x383906a52  test    byte ptr cs:_bidGblFlags, 4
0x383906a59  jz      loc_38389215D
0x383906a5f  mov     rcx, cs:_bidID
0x383906a66  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383906a6a  jz      loc_38389215D
0x383906a70  lea     r9, [rsp+48h+arg_0]
0x383906a75  xor     r8d, r8d
0x383906a78  xor     edx, edx
0x383906a7a  call    cs:off_383B15058
0x383906a80  nop
0x383906a81  jmp     loc_38389215D
0x383906a86  call    cs:__imp_SetLastError
0x383906a8c  call    cs:__imp_GetLastError
0x383906a92  mov     ebx, eax
0x383906a94  call    ?SpnTerminate@SNI_Spn@@SAXXZ; SNI_Spn::SpnTerminate(void)
0x383906a99  mov     r11d, cs:_bidGblFlags
0x383906aa0  and     r11d, 20002h
0x383906aa7  cmp     r11d, 20002h
0x383906aae  jnz     short loc_383906AD8
0x383906ab0  mov     rcx, cs:off_383B48040; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x383906ab7  test    rcx, rcx
0x383906aba  jz      short loc_383906AD8
0x383906abc  mov     r9d, ebx
0x383906abf  mov     r8, cs:off_383B48040; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x383906ac6  mov     edx, 2B000h
0x383906acb  mov     rcx, cs:off_383B459C0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383906ad2  call    _bidTraceA
0x383906ad7  nop
0x383906ad8  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383906ade  jz      short loc_383906B06
0x383906ae0  test    byte ptr cs:_bidGblFlags, 4
0x383906ae7  jz      short loc_383906B06
0x383906ae9  mov     rcx, cs:_bidID
0x383906af0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383906af4  jz      short loc_383906B06
0x383906af6  lea     r9, [rsp+48h+arg_0]
0x383906afb  xor     r8d, r8d
0x383906afe  xor     edx, edx
0x383906b00  call    cs:off_383B15058
0x383906b06  mov     eax, ebx
0x383906b08  jmp     loc_383892161
```
