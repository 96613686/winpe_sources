# GetClassifiedObject<EventSourceCollection>(void *,ObjectType,wmi::AutoRef<EventSourceCollection> &)

- ea: `0x1800027ec`
- end: `0x1800028fa`
- name: `??$GetClassifiedObject@VEventSourceCollection@@@@YAXPEAXW4ObjectType@@AEAV?$AutoRef@VEventSourceCollection@@@wmi@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180004940`
- `0x180004b50`
- `0x180005190`
- `0x180005720`
- `0x180005a00`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x1800027ec`
- `0x180003970`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetClassifiedObject<EventSourceCollection>(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 (__fastcall ***v5)(_QWORD, __int64); // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  _BYTE pExceptionObject[64]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+88h] [rbp+20h] BYREF

  v9 = 0;
  result = ObjectTable<wmi::AutoRef<Object>>::Get(a1, (unsigned int)a1, &v9);
  if ( !(_BYTE)result || (v5 = (__int64 (__fastcall ***)(_QWORD, __int64))v9, *(_DWORD *)(v9 + 16) != 3) )
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
0x1800027ec  mov     rax, rsp
0x1800027ef  mov     [rax+8], rbx
0x1800027f3  mov     [rax+18h], rsi
0x1800027f7  push    rdi
0x1800027f8  sub     rsp, 60h
0x1800027fc  mov     rsi, r8
0x1800027ff  mov     qword ptr [rax+20h], 0
0x180002807  mov     edx, ecx
0x180002809  lea     r8, [rax+20h]
0x18000280d  call    ?Get@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@QEAA_NKAEAV?$AutoRef@VObject@@@wmi@@@Z; ObjectTable<wmi::AutoRef<Object>>::Get(ulong,wmi::AutoRef<Object> &)
0x180002812  test    al, al
0x180002814  jz      short loc_180002895
0x180002816  mov     rbx, [rsp+68h+arg_18]
0x18000281e  cmp     dword ptr [rbx+10h], 3
0x180002822  jnz     short loc_180002895
0x180002824  test    rbx, rbx
0x180002827  jz      short loc_180002832
0x180002829  lea     rdi, [rbx+8]
0x18000282d  lock inc dword ptr [rdi]
0x180002830  jmp     short loc_180002837
0x180002832  mov     edi, 8
0x180002837  mov     rcx, [rsi]
0x18000283a  test    rcx, rcx
0x18000283d  jz      short loc_18000285C
0x18000283f  or      eax, 0FFFFFFFFh
0x180002842  lock xadd [rcx+8], eax
0x180002847  cmp     eax, 1
0x18000284a  jnz     short loc_18000285C
0x18000284c  mov     rax, [rcx]
0x18000284f  mov     edx, 1
0x180002854  mov     rax, [rax]
0x180002857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000285c  mov     [rsi], rbx
0x18000285f  test    rbx, rbx
0x180002862  jz      short loc_180002883
0x180002864  or      eax, 0FFFFFFFFh
0x180002867  lock xadd [rdi], eax
0x18000286b  cmp     eax, 1
0x18000286e  jnz     short loc_180002883
0x180002870  mov     rax, [rbx]
0x180002873  mov     edx, 1
0x180002878  mov     rcx, rbx
0x18000287b  mov     rax, [rax]
0x18000287e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002883  lea     r11, [rsp+68h+var_8]
0x180002888  mov     rbx, [r11+10h]
0x18000288c  mov     rsi, [r11+20h]
0x180002890  mov     rsp, r11
0x180002893  pop     rdi
0x180002894  retn
0x180002895  lea     rax, WPP_GLOBAL_Control
0x18000289c  mov     ebx, 6
0x1800028a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028a8  cmp     rcx, rax
0x1800028ab  jz      short loc_1800028CF
0x1800028ad  test    byte ptr [rcx+1Ch], 1
0x1800028b1  jz      short loc_1800028CF
0x1800028b3  cmp     byte ptr [rcx+19h], 2
0x1800028b7  jb      short loc_1800028CF
0x1800028b9  lea     edx, [rbx+4]
0x1800028bc  mov     r9d, ebx
0x1800028bf  lea     r8, WPP_da08efde17a138a495075faea6342aa5_Traceguids
0x1800028c6  mov     rcx, [rcx+10h]
0x1800028ca  call    WPP_SF_D
0x1800028cf  mov     r9d, 0CAh; int
0x1800028d5  lea     r8, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x1800028dc  mov     edx, ebx; unsigned int
0x1800028de  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800028e3  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800028e8  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800028ef  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800028f4  call    _CxxThrowException_0
```
