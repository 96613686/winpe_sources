# SchdpExecuteTask(void)

- ea: `0x180006f20`
- end: `0x1800072c6`
- name: `?SchdpExecuteTask@@YAJXZ`
- size: `934`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800076e0`

## callees

- `0x180006f20`
- `0x18000b13c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006f7a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006f7a`

## string_xrefs

- `0x180007230`: `SchdpExecuteTask`
- `0x18000702e`: `Scheduled`
- `0x18000710e`: `Scheduled`
- `0x1800071c2`: `Scheduled`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SchdpExecuteTask(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  int v2; // r8d
  __int64 v3; // rax
  __int64 (__fastcall *v4)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rax
  __int64 (__fastcall *v5)(__int64, const wchar_t *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, _QWORD); // rax
  __int64 v6; // rax
  __int64 (__fastcall *v7)(__int64, const wchar_t *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, _QWORD); // rax
  _QWORD v9[4]; // [rsp+50h] [rbp-69h] BYREF
  __int128 v10; // [rsp+70h] [rbp-49h] BYREF
  __int64 v11; // [rsp+80h] [rbp-39h]
  __int128 v12; // [rsp+90h] [rbp-29h] BYREF
  __int64 v13; // [rsp+A0h] [rbp-19h]
  __int128 v14; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v15; // [rsp+C0h] [rbp+7h]
  __int128 v16; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v17; // [rsp+E0h] [rbp+27h]
  __int64 v18; // [rsp+120h] [rbp+67h] BYREF
  __int64 v19; // [rsp+128h] [rbp+6Fh] BYREF
  LPVOID ppv; // [rsp+130h] [rbp+77h] BYREF
  __int64 *v21; // [rsp+138h] [rbp+7Fh] BYREF

  ppv = 0;
  v18 = 0;
  v21 = 0;
  v19 = 0;
  memset(v9, 0, sizeof(v9));
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v16 = *(_OWORD *)&v9[1];
    v3 = *(_QWORD *)ppv;
    v17 = v9[3];
    v12 = *(_OWORD *)&v9[1];
    v13 = v9[3];
    v4 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(v3 + 80);
    v14 = *(_OWORD *)&v9[1];
    v15 = v9[3];
    v10 = *(_OWORD *)&v9[1];
    v11 = v9[3];
    v0 = v4(ppv, &v10, &v14, &v12, &v16);
    v1 = v0;
    if ( v0 >= 0 )
    {
      v0 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL))(
             ppv,
             L"\\Microsoft\\Windows\\Diagnosis",
             &v18);
      v1 = v0;
      if ( v0 >= 0 )
      {
        v0 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 **))(*(_QWORD *)v18 + 104LL))(
               v18,
               L"Scheduled",
               &v21);
        v1 = v0;
        if ( v0 >= 0 )
        {
          v0 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v21 + 152))(v21, &v19);
          v1 = v0;
          if ( v0 >= 0 )
          {
            v0 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v19 + 88LL))(v19, v9);
            v1 = v0;
            if ( v0 >= 0 )
            {
              v0 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v9[0] + 336LL))(v9[0], 0);
              v1 = v0;
              if ( v0 >= 0 )
              {
                v5 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, _QWORD))(*(_QWORD *)v18 + 136LL);
                v10 = *(_OWORD *)&v9[1];
                v11 = v9[3];
                v14 = *(_OWORD *)&v9[1];
                v15 = v9[3];
                v12 = *(_OWORD *)&v9[1];
                v13 = v9[3];
                v0 = v5(v18, L"Scheduled", v19, 4, &v12, &v14, 3, &v10, 0);
                v1 = v0;
                if ( v0 >= 0 )
                {
                  v6 = *v21;
                  v10 = *(_OWORD *)&v9[1];
                  v11 = v9[3];
                  v0 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD, _QWORD, _QWORD, _QWORD))(v6 + 104))(
                         v21,
                         &v10,
                         0,
                         0,
                         0,
                         0);
                  v1 = v0;
                  if ( v0 >= 0 )
                  {
                    v0 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v9[0] + 336LL))(v9[0], 0xFFFFFFFFLL);
                    v1 = v0;
                    if ( v0 >= 0 )
                    {
                      v7 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64, __int128 *, __int128 *, int, __int128 *, _QWORD))(*(_QWORD *)v18 + 136LL);
                      v10 = *(_OWORD *)&v9[1];
                      v11 = v9[3];
                      v14 = *(_OWORD *)&v9[1];
                      v15 = v9[3];
                      v12 = *(_OWORD *)&v9[1];
                      v13 = v9[3];
                      v0 = v7(v18, L"Scheduled", v19, 4, &v12, &v14, 3, &v10, 0);
                      v1 = v0;
                      if ( v0 >= 0 )
                        goto LABEL_24;
                      v2 = 485;
                    }
                    else
                    {
                      v2 = 475;
                    }
                  }
                  else
                  {
                    v2 = 472;
                  }
                }
                else
                {
                  v2 = 469;
                }
              }
              else
              {
                v2 = 459;
              }
            }
            else
            {
              v2 = 456;
            }
          }
          else
          {
            v2 = 453;
          }
        }
        else
        {
          v2 = 450;
        }
      }
      else
      {
        v2 = 447;
      }
    }
    else
    {
      v2 = 444;
    }
  }
  else
  {
    v2 = 441;
  }
  SdpDebugTrace(1u, L"SchdpExecuteTask", v2, v0);
LABEL_24:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    v21 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v9[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
  return v1;
}

```

## disassembly

```asm
0x180006f20  push    rbp
0x180006f22  push    rbx
0x180006f23  push    rsi
0x180006f24  push    rdi
0x180006f25  lea     rbp, [rsp-3Fh]
0x180006f2a  sub     rsp, 0F8h
0x180006f31  xor     edi, edi
0x180006f33  lea     r9, IID_ITaskService; riid
0x180006f3a  xor     eax, eax
0x180006f3c  mov     [rbp+57h+arg_10], rdi
0x180006f40  mov     [rbp+57h+var_A6], eax
0x180006f43  lea     rcx, CLSID_TaskScheduler; rclsid
0x180006f4a  mov     [rbp+57h+var_A2], ax
0x180006f4e  xorps   xmm0, xmm0
0x180006f51  lea     rax, [rbp+57h+arg_10]
0x180006f55  mov     [rbp+57h+arg_0], rdi
0x180006f59  lea     esi, [rdi+1]
0x180006f5c  mov     [rbp+57h+arg_18], rdi
0x180006f60  mov     r8d, esi; dwClsContext
0x180006f63  mov     [rbp+57h+arg_8], rdi
0x180006f67  xor     edx, edx; pUnkOuter
0x180006f69  mov     [rbp+57h+var_C0], rdi
0x180006f6d  mov     word ptr [rbp+57h+var_B8], di
0x180006f71  movups  [rbp+57h+var_B8+2], xmm0
0x180006f75  mov     [rsp+110h+ppv], rax; ppv
0x180006f7a  call    cs:__imp_CoCreateInstance
0x180006f81  nop     dword ptr [rax+rax+00h]
0x180006f86  mov     ebx, eax
0x180006f88  test    eax, eax
0x180006f8a  jns     short loc_180006F97
0x180006f8c  mov     r8d, 1B9h
0x180006f92  jmp     loc_18000722D
0x180006f97  movups  xmm0, [rbp+57h+var_B8]
0x180006f9b  lea     rdx, [rbp+57h+var_40]
0x180006f9f  mov     rcx, [rbp+57h+arg_10]
0x180006fa3  movsd   xmm1, qword ptr [rbp-51h]
0x180006fa8  lea     r9, [rbp+57h+var_80]
0x180006fac  mov     [rsp+110h+ppv], rdx
0x180006fb1  lea     r8, [rbp+57h+var_60]
0x180006fb5  lea     rdx, [rbp+57h+var_A0]
0x180006fb9  movaps  [rbp+57h+var_40], xmm0
0x180006fbd  mov     rax, [rcx]
0x180006fc0  movsd   [rbp+57h+var_30], xmm1
0x180006fc5  movaps  [rbp+57h+var_80], xmm0
0x180006fc9  movsd   [rbp+57h+var_70], xmm1
0x180006fce  mov     rax, [rax+50h]
0x180006fd2  movaps  [rbp+57h+var_60], xmm0
0x180006fd6  movsd   [rbp+57h+var_50], xmm1
0x180006fdb  movaps  [rbp+57h+var_A0], xmm0
0x180006fdf  movsd   [rbp+57h+var_90], xmm1
0x180006fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe9  mov     ebx, eax
0x180006feb  test    eax, eax
0x180006fed  jns     short loc_180006FFA
0x180006fef  mov     r8d, 1BCh
0x180006ff5  jmp     loc_18000722D
0x180006ffa  mov     rcx, [rbp+57h+arg_10]
0x180006ffe  lea     r8, [rbp+57h+arg_0]
0x180007002  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Diagnosis"
0x180007009  mov     rax, [rcx]
0x18000700c  mov     rax, [rax+38h]
0x180007010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007015  mov     ebx, eax
0x180007017  test    eax, eax
0x180007019  jns     short loc_180007026
0x18000701b  mov     r8d, 1BFh
0x180007021  jmp     loc_18000722D
0x180007026  mov     rcx, [rbp+57h+arg_0]
0x18000702a  lea     r8, [rbp+57h+arg_18]
0x18000702e  lea     rdx, aScheduled; "Scheduled"
0x180007035  mov     rax, [rcx]
0x180007038  mov     rax, [rax+68h]
0x18000703c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007041  mov     ebx, eax
0x180007043  test    eax, eax
0x180007045  jns     short loc_180007052
0x180007047  mov     r8d, 1C2h
0x18000704d  jmp     loc_18000722D
0x180007052  mov     rcx, [rbp+57h+arg_18]
0x180007056  lea     rdx, [rbp+57h+arg_8]
0x18000705a  mov     rax, [rcx]
0x18000705d  mov     rax, [rax+98h]
0x180007064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007069  mov     ebx, eax
0x18000706b  test    eax, eax
0x18000706d  jns     short loc_18000707A
0x18000706f  mov     r8d, 1C5h
0x180007075  jmp     loc_18000722D
0x18000707a  mov     rcx, [rbp+57h+arg_8]
0x18000707e  lea     rdx, [rbp+57h+var_C0]
0x180007082  mov     rax, [rcx]
0x180007085  mov     rax, [rax+58h]
0x180007089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000708e  mov     ebx, eax
0x180007090  test    eax, eax
0x180007092  jns     short loc_18000709F
0x180007094  mov     r8d, 1C8h
0x18000709a  jmp     loc_18000722D
0x18000709f  mov     rcx, [rbp+57h+var_C0]
0x1800070a3  xor     edx, edx
0x1800070a5  mov     rax, [rcx]
0x1800070a8  mov     rax, [rax+150h]
0x1800070af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b4  mov     ebx, eax
0x1800070b6  test    eax, eax
0x1800070b8  jns     short loc_1800070C5
0x1800070ba  mov     r8d, 1CBh
0x1800070c0  jmp     loc_18000722D
0x1800070c5  movups  xmm0, [rbp+57h+var_B8]
0x1800070c9  lea     rdx, [rbp+57h+var_A0]
0x1800070cd  mov     rcx, [rbp+57h+arg_0]
0x1800070d1  movsd   xmm1, qword ptr [rbp-51h]
0x1800070d6  mov     r9d, 4
0x1800070dc  mov     r8, [rbp+57h+arg_8]
0x1800070e0  mov     [rsp+110h+var_D0], rdi
0x1800070e5  mov     rax, [rcx]
0x1800070e8  mov     [rsp+110h+var_D8], rdx
0x1800070ed  lea     rdx, [rbp+57h+var_60]
0x1800070f1  mov     [rsp+110h+var_E0], 3
0x1800070f9  mov     [rsp+110h+var_E8], rdx
0x1800070fe  lea     rdx, [rbp+57h+var_80]
0x180007102  mov     rax, [rax+88h]
0x180007109  mov     [rsp+110h+ppv], rdx
0x18000710e  lea     rdx, aScheduled; "Scheduled"
0x180007115  movaps  [rbp+57h+var_A0], xmm0
0x180007119  movsd   [rbp+57h+var_90], xmm1
0x18000711e  movaps  [rbp+57h+var_60], xmm0
0x180007122  movsd   [rbp+57h+var_50], xmm1
0x180007127  movaps  [rbp+57h+var_80], xmm0
0x18000712b  movsd   [rbp+57h+var_70], xmm1
0x180007130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007135  mov     ebx, eax
0x180007137  test    eax, eax
0x180007139  jns     short loc_180007146
0x18000713b  mov     r8d, 1D5h
0x180007141  jmp     loc_18000722D
0x180007146  mov     rcx, [rbp+57h+arg_18]
0x18000714a  lea     rdx, [rbp+57h+var_A0]
0x18000714e  movups  xmm0, [rbp+57h+var_B8]
0x180007152  xor     r9d, r9d
0x180007155  mov     [rsp+110h+var_E8], rdi
0x18000715a  movsd   xmm1, qword ptr [rbp-51h]
0x18000715f  xor     r8d, r8d
0x180007162  mov     rax, [rcx]
0x180007165  movaps  [rbp+57h+var_A0], xmm0
0x180007169  movsd   [rbp+57h+var_90], xmm1
0x18000716e  mov     [rsp+110h+ppv], rdi
0x180007173  mov     rax, [rax+68h]
0x180007177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717c  mov     ebx, eax
0x18000717e  test    eax, eax
0x180007180  jns     short loc_18000718D
0x180007182  mov     r8d, 1D8h
0x180007188  jmp     loc_18000722D
0x18000718d  mov     rcx, [rbp+57h+var_C0]
0x180007191  or      edx, 0FFFFFFFFh
0x180007194  mov     rax, [rcx]
0x180007197  mov     rax, [rax+150h]
0x18000719e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a3  mov     ebx, eax
0x1800071a5  test    eax, eax
0x1800071a7  jns     short loc_1800071B1
0x1800071a9  mov     r8d, 1DBh
0x1800071af  jmp     short loc_18000722D
0x1800071b1  movups  xmm0, [rbp+57h+var_B8]
0x1800071b5  lea     r8, [rbp+57h+var_A0]
0x1800071b9  mov     rcx, [rbp+57h+arg_0]
0x1800071bd  movsd   xmm1, qword ptr [rbp-51h]
0x1800071c2  lea     rdx, aScheduled; "Scheduled"
0x1800071c9  mov     [rsp+110h+var_D0], rdi
0x1800071ce  mov     r9d, 4
0x1800071d4  mov     [rsp+110h+var_D8], r8
0x1800071d9  lea     r8, [rbp+57h+var_60]
0x1800071dd  mov     rax, [rcx]
0x1800071e0  mov     [rsp+110h+var_E0], 3
0x1800071e8  mov     [rsp+110h+var_E8], r8
0x1800071ed  lea     r8, [rbp+57h+var_80]
0x1800071f1  mov     [rsp+110h+ppv], r8
0x1800071f6  mov     rax, [rax+88h]
0x1800071fd  mov     r8, [rbp+57h+arg_8]
0x180007201  movaps  [rbp+57h+var_A0], xmm0
0x180007205  movsd   [rbp+57h+var_90], xmm1
0x18000720a  movaps  [rbp+57h+var_60], xmm0
0x18000720e  movsd   [rbp+57h+var_50], xmm1
0x180007213  movaps  [rbp+57h+var_80], xmm0
0x180007217  movsd   [rbp+57h+var_70], xmm1
0x18000721c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007221  mov     ebx, eax
0x180007223  test    eax, eax
0x180007225  jns     short loc_18000723E
0x180007227  mov     r8d, 1E5h; int
0x18000722d  mov     r9d, eax; int
0x180007230  lea     rdx, aSchdpexecuteta; "SchdpExecuteTask"
0x180007237  mov     ecx, esi; Level
0x180007239  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000723e  mov     rcx, [rbp+57h+arg_10]
0x180007242  test    rcx, rcx
0x180007245  jz      short loc_180007257
0x180007247  mov     rax, [rcx]
0x18000724a  mov     rax, [rax+10h]
0x18000724e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007253  mov     [rbp+57h+arg_10], rdi
0x180007257  mov     rcx, [rbp+57h+arg_0]
0x18000725b  test    rcx, rcx
0x18000725e  jz      short loc_180007270
0x180007260  mov     rax, [rcx]
0x180007263  mov     rax, [rax+10h]
0x180007267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000726c  mov     [rbp+57h+arg_0], rdi
0x180007270  mov     rcx, [rbp+57h+arg_18]
0x180007274  test    rcx, rcx
0x180007277  jz      short loc_180007289
0x180007279  mov     rax, [rcx]
0x18000727c  mov     rax, [rax+10h]
0x180007280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007285  mov     [rbp+57h+arg_18], rdi
0x180007289  mov     rcx, [rbp+57h+arg_8]
0x18000728d  test    rcx, rcx
0x180007290  jz      short loc_1800072A2
0x180007292  mov     rax, [rcx]
0x180007295  mov     rax, [rax+10h]
0x180007299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000729e  mov     [rbp+57h+arg_8], rdi
0x1800072a2  mov     rcx, [rbp+57h+var_C0]
0x1800072a6  test    rcx, rcx
0x1800072a9  jz      short loc_1800072B7
0x1800072ab  mov     rax, [rcx]
0x1800072ae  mov     rax, [rax+10h]
0x1800072b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b7  mov     eax, ebx
0x1800072b9  add     rsp, 0F8h
0x1800072c0  pop     rdi
0x1800072c1  pop     rsi
0x1800072c2  pop     rbx
0x1800072c3  pop     rbp
0x1800072c4  retn
```
