# GetClassifiedObject<Subscription>(void *,ObjectType,wmi::AutoRef<Subscription> &)

- ea: `0x180002900`
- end: `0x180002a0e`
- name: `??$GetClassifiedObject@VSubscription@@@@YAXPEAXW4ObjectType@@AEAV?$AutoRef@VSubscription@@@wmi@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x180004b50`
- `0x180004cc0`
- `0x180005900`
- `0x180005b90`
- `0x180005e2c`
- `0x1800064e8`
- `0x180006fb8`
- `0x1800073c4`
- `0x180007720`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x180002900`
- `0x180003970`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall GetClassifiedObject<Subscription>(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 (__fastcall ***v5)(_QWORD, __int64); // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  _BYTE pExceptionObject[64]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+88h] [rbp+20h] BYREF

  v9 = 0;
  result = ObjectTable<wmi::AutoRef<Object>>::Get(a1, (unsigned int)a1, &v9);
  if ( !(_BYTE)result || (v5 = (__int64 (__fastcall ***)(_QWORD, __int64))v9, *(_DWORD *)(v9 + 16) != 1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xAu,
        (const GUID *)WPP_da08efde17a138a495075faea6342aa5_Traceguids,
        6);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      6,
      "admin\\wmi\\events\\forwarding\\collector\\api\\apiobj.h",
      202);
    throw (wmi::GenericException *)pExceptionObject;
  }
  if ( v9 )
  {
    v6 = v9 + 8;
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  }
  else
  {
    v6 = 8;
  }
  v7 = *a3;
  if ( *a3 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      result = (**(__int64 (__fastcall ***)(__int64, __int64))v7)(v7, 1);
  }
  *a3 = (__int64)v5;
  if ( v5 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      return (**v5)(v5, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180002900  mov     rax, rsp
0x180002903  mov     [rax+8], rbx
0x180002907  mov     [rax+18h], rsi
0x18000290b  push    rdi
0x18000290c  sub     rsp, 60h
0x180002910  mov     rsi, r8
0x180002913  mov     qword ptr [rax+20h], 0
0x18000291b  mov     edx, ecx
0x18000291d  lea     r8, [rax+20h]
0x180002921  call    ?Get@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@QEAA_NKAEAV?$AutoRef@VObject@@@wmi@@@Z; ObjectTable<wmi::AutoRef<Object>>::Get(ulong,wmi::AutoRef<Object> &)
0x180002926  test    al, al
0x180002928  jz      short loc_1800029A9
0x18000292a  mov     rbx, [rsp+68h+arg_18]
0x180002932  cmp     dword ptr [rbx+10h], 1
0x180002936  jnz     short loc_1800029A9
0x180002938  test    rbx, rbx
0x18000293b  jz      short loc_180002946
0x18000293d  lea     rdi, [rbx+8]
0x180002941  lock inc dword ptr [rdi]
0x180002944  jmp     short loc_18000294B
0x180002946  mov     edi, 8
0x18000294b  mov     rcx, [rsi]
0x18000294e  test    rcx, rcx
0x180002951  jz      short loc_180002970
0x180002953  or      eax, 0FFFFFFFFh
0x180002956  lock xadd [rcx+8], eax
0x18000295b  cmp     eax, 1
0x18000295e  jnz     short loc_180002970
0x180002960  mov     rax, [rcx]
0x180002963  mov     edx, 1
0x180002968  mov     rax, [rax]
0x18000296b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002970  mov     [rsi], rbx
0x180002973  test    rbx, rbx
0x180002976  jz      short loc_180002997
0x180002978  or      eax, 0FFFFFFFFh
0x18000297b  lock xadd [rdi], eax
0x18000297f  cmp     eax, 1
0x180002982  jnz     short loc_180002997
0x180002984  mov     rax, [rbx]
0x180002987  mov     edx, 1
0x18000298c  mov     rcx, rbx
0x18000298f  mov     rax, [rax]
0x180002992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002997  lea     r11, [rsp+68h+var_8]
0x18000299c  mov     rbx, [r11+10h]
0x1800029a0  mov     rsi, [r11+20h]
0x1800029a4  mov     rsp, r11
0x1800029a7  pop     rdi
0x1800029a8  retn
0x1800029a9  lea     rax, WPP_GLOBAL_Control
0x1800029b0  mov     ebx, 6
0x1800029b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029bc  cmp     rcx, rax
0x1800029bf  jz      short loc_1800029E3
0x1800029c1  test    byte ptr [rcx+1Ch], 1
0x1800029c5  jz      short loc_1800029E3
0x1800029c7  cmp     byte ptr [rcx+19h], 2
0x1800029cb  jb      short loc_1800029E3
0x1800029cd  lea     edx, [rbx+4]
0x1800029d0  mov     r9d, ebx
0x1800029d3  lea     r8, WPP_da08efde17a138a495075faea6342aa5_Traceguids
0x1800029da  mov     rcx, [rcx+10h]
0x1800029de  call    WPP_SF_D
0x1800029e3  mov     r9d, 0CAh; int
0x1800029e9  lea     r8, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x1800029f0  mov     edx, ebx; unsigned int
0x1800029f2  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800029f7  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800029fc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002a03  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180002a08  call    _CxxThrowException_0
```
