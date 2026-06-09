# SensFirePowerEventHelper(_SYSTEM_POWER_STATUS,SENS_EVENT_TYPE)

- ea: `0x180004828`
- end: `0x1800049d8`
- name: `?SensFirePowerEventHelper@@YAJU_SYSTEM_POWER_STATUS@@W4SENS_EVENT_TYPE@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000478c`

## callees

- `0x180004828`
- `0x180008300`
- `0x1800093b0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004860`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004860`

## pseudocode

```c
__int64 __fastcall SensFirePowerEventHelper(__int64 a1, unsigned int a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  _BYTE *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v10; // eax
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&SENSGUID_EVENTCLASS_ONNOW, 0, 0x15u, &IID_ISensOnNow, &ppv);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    switch ( a2 )
    {
      case 0xEu:
        v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, 0);
        break;
      case 0xFu:
        v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, *(unsigned __int8 *)(a1 + 2));
        break;
      case 0x10u:
        v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, *(unsigned __int8 *)(a1 + 2));
        break;
      default:
        if ( v6 == (_BYTE *)&WPP_GLOBAL_Control )
          goto LABEL_24;
        if ( (v6[28] & 1) == 0 || v6[25] < 3u )
          goto LABEL_18;
        WPP_SF_d(*((_QWORD *)v6 + 2), 51, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, a2);
LABEL_17:
        v6 = WPP_GLOBAL_Control;
LABEL_18:
        if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[28] & 1) == 0 || v6[25] < 5u )
          goto LABEL_24;
        v7 = 53;
        goto LABEL_22;
    }
    v5 = v10;
    if ( v10 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v7 = 52;
LABEL_22:
      v8 = v5;
      goto LABEL_23;
    }
    goto LABEL_17;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 49;
    v8 = (unsigned int)v4;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, v8);
  }
LABEL_24:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v5;
}

```

## disassembly

```asm
0x180004828  push    rbx
0x18000482a  push    rsi
0x18000482b  push    r14
0x18000482d  push    r15
0x18000482f  sub     rsp, 38h
0x180004833  mov     r14d, edx
0x180004836  mov     [rsp+58h+arg_10], 0
0x18000483f  xor     edx, edx; pUnkOuter
0x180004841  lea     rax, [rsp+58h+arg_10]
0x180004846  mov     r15, rcx
0x180004849  mov     [rsp+58h+ppv], rax; ppv
0x18000484e  lea     r9, IID_ISensOnNow; riid
0x180004855  lea     rcx, SENSGUID_EVENTCLASS_ONNOW; rclsid
0x18000485c  lea     r8d, [rdx+15h]; dwClsContext
0x180004860  call    cs:__imp_CoCreateInstance
0x180004866  mov     ebx, eax
0x180004868  test    eax, eax
0x18000486a  jns     short loc_1800048A4
0x18000486c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004873  lea     rsi, WPP_GLOBAL_Control
0x18000487a  cmp     rcx, rsi
0x18000487d  jz      loc_180004952
0x180004883  test    byte ptr [rcx+1Ch], 1
0x180004887  jz      loc_180004952
0x18000488d  cmp     byte ptr [rcx+19h], 2
0x180004891  jb      loc_180004952
0x180004897  mov     edx, 31h ; '1'
0x18000489c  mov     r9d, eax
0x18000489f  jmp     loc_180004942
0x1800048a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048ab  lea     rsi, WPP_GLOBAL_Control
0x1800048b2  cmp     rcx, rsi
0x1800048b5  jz      short loc_1800048DF
0x1800048b7  test    byte ptr [rcx+1Ch], 1
0x1800048bb  jz      short loc_1800048DF
0x1800048bd  cmp     byte ptr [rcx+19h], 5
0x1800048c1  jb      short loc_1800048DF
0x1800048c3  mov     rcx, [rcx+10h]
0x1800048c7  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x1800048ce  mov     edx, 32h ; '2'
0x1800048d3  call    WPP_SF_
0x1800048d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048df  mov     edx, r14d
0x1800048e2  sub     edx, 0Eh
0x1800048e5  jz      loc_18000499B
0x1800048eb  sub     edx, 1
0x1800048ee  jz      loc_18000498D
0x1800048f4  cmp     edx, 1
0x1800048f7  jz      short loc_180004975
0x1800048f9  cmp     rcx, rsi
0x1800048fc  jz      short loc_180004952
0x1800048fe  test    byte ptr [rcx+1Ch], 1
0x180004902  jz      short loc_180004929
0x180004904  cmp     byte ptr [rcx+19h], 3
0x180004908  jb      short loc_180004929
0x18000490a  mov     rcx, [rcx+10h]
0x18000490e  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180004915  mov     edx, 33h ; '3'
0x18000491a  mov     r9d, r14d
0x18000491d  call    WPP_SF_d
0x180004922  mov     rcx, cs:WPP_GLOBAL_Control
0x180004929  cmp     rcx, rsi
0x18000492c  jz      short loc_180004952
0x18000492e  test    byte ptr [rcx+1Ch], 1
0x180004932  jz      short loc_180004952
0x180004934  cmp     byte ptr [rcx+19h], 5
0x180004938  jb      short loc_180004952
0x18000493a  mov     edx, 35h ; '5'
0x18000493f  mov     r9d, ebx
0x180004942  mov     rcx, [rcx+10h]
0x180004946  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x18000494d  call    WPP_SF_d
0x180004952  mov     rcx, [rsp+58h+arg_10]
0x180004957  test    rcx, rcx
0x18000495a  jz      short loc_180004968
0x18000495c  mov     rax, [rcx]
0x18000495f  mov     rax, [rax+10h]
0x180004963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004968  mov     eax, ebx
0x18000496a  add     rsp, 38h
0x18000496e  pop     r15
0x180004970  pop     r14
0x180004972  pop     rsi
0x180004973  pop     rbx
0x180004974  retn
0x180004975  mov     rcx, [rsp+58h+arg_10]
0x18000497a  mov     rax, [rcx]
0x18000497d  mov     rax, [rax+48h]
0x180004981  movzx   edx, byte ptr [r15+2]
0x180004986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000498b  jmp     short loc_1800049AC
0x18000498d  mov     rcx, [rsp+58h+arg_10]
0x180004992  mov     rax, [rcx]
0x180004995  mov     rax, [rax+40h]
0x180004999  jmp     short loc_180004981
0x18000499b  mov     rcx, [rsp+58h+arg_10]
0x1800049a0  mov     rax, [rcx]
0x1800049a3  mov     rax, [rax+38h]
0x1800049a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ac  mov     ebx, eax
0x1800049ae  test    eax, eax
0x1800049b0  jns     loc_180004922
0x1800049b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049bd  cmp     rcx, rsi
0x1800049c0  jz      short loc_180004952
0x1800049c2  test    byte ptr [rcx+1Ch], 1
0x1800049c6  jz      short loc_180004952
0x1800049c8  cmp     byte ptr [rcx+19h], 2
0x1800049cc  jb      short loc_180004952
0x1800049ce  mov     edx, 34h ; '4'
0x1800049d3  jmp     loc_18000493F
```
