# CWdsComMetadataBuilder::AppendSystemtimeEntry(ushort *,double)

- ea: `0x18000f470`
- end: `0x18000f580`
- name: `?AppendSystemtimeEntry@CWdsComMetadataBuilder@@UEAAJPEAGN@Z`
- size: `272`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, double)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000be10`
- `0x18000e3e4`
- `0x18000f470`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f4a5`
- `KERNEL32!EnterCriticalSection` at `0x18000f4a5`
- `KERNEL32!LeaveCriticalSection` at `0x18000f556`
- `KERNEL32!LeaveCriticalSection` at `0x18000f556`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18000f4e8`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18000f4e8`

## string_xrefs

- `0x18000f4c8`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f4f7`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f531`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendSystemtimeEntry(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        DOUBLE a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v6; // ebx
  const char *v7; // rdx
  const char *v8; // rdx
  signed int appended; // edi
  const char *v10; // rdx
  struct _SYSTEMTIME v12; // [rsp+20h] [rbp-58h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-48h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  *(_QWORD *)&SystemTime.wYear = 0;
  *(_QWORD *)&SystemTime.wHour = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2)
    || (v6 = -2147024809,
        (int)ElValidateHr(-2147024809, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x3D7u) >= 0) )
  {
    if ( VariantTimeToSystemTime(a3, &SystemTime)
      || (v6 = -2147418113,
          (int)ElValidateHr(-2147418113, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x3DDu) >= 0) )
    {
      v12 = SystemTime;
      appended = CWdsMetadata::AppendTimeEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2, &v12);
      if ( ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x3E1u) )
      {
        v6 = (unsigned __int16)appended | 0x80070000;
        if ( appended <= 0 )
          v6 = appended;
      }
    }
  }
  LeaveCriticalSection(v3);
  return v6;
}

```

## disassembly

```asm
0x18000f470  mov     [rsp+arg_18], rbx
0x18000f475  push    rbp
0x18000f476  push    rsi
0x18000f477  push    rdi
0x18000f478  sub     rsp, 60h
0x18000f47c  movaps  [rsp+78h+var_28], xmm6
0x18000f481  mov     rax, cs:__security_cookie
0x18000f488  xor     rax, rsp
0x18000f48b  mov     [rsp+78h+var_38], rax
0x18000f490  lea     rsi, [rcx+88h]
0x18000f497  mov     rdi, rcx
0x18000f49a  mov     rcx, rsi; lpCriticalSection
0x18000f49d  movaps  xmm6, xmm2
0x18000f4a0  mov     rbp, rdx
0x18000f4a3  xor     ebx, ebx
0x18000f4a5  call    cs:__imp_EnterCriticalSection
0x18000f4ab  xor     eax, eax
0x18000f4ad  mov     rcx, rbp; pbstr
0x18000f4b0  mov     qword ptr [rsp+78h+SystemTime.wYear], rax
0x18000f4b5  mov     qword ptr [rsp+78h+SystemTime.wHour], rax
0x18000f4ba  call    ValidateNonEmptyBstr
0x18000f4bf  test    eax, eax
0x18000f4c1  jnz     short loc_18000F4E0
0x18000f4c3  mov     ebx, 80070057h
0x18000f4c8  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f4cf  mov     ecx, ebx; int
0x18000f4d1  mov     r9d, 3D7h; unsigned int
0x18000f4d7  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f4dc  test    eax, eax
0x18000f4de  js      short loc_18000F553
0x18000f4e0  lea     rdx, [rsp+78h+SystemTime]; lpSystemTime
0x18000f4e5  movaps  xmm0, xmm6; vtime
0x18000f4e8  call    cs:__imp_VariantTimeToSystemTime
0x18000f4ee  test    eax, eax
0x18000f4f0  jnz     short loc_18000F50F
0x18000f4f2  mov     ebx, 8000FFFFh
0x18000f4f7  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f4fe  mov     ecx, ebx; int
0x18000f500  mov     r9d, 3DDh; unsigned int
0x18000f506  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f50b  test    eax, eax
0x18000f50d  js      short loc_18000F553
0x18000f50f  movaps  xmm0, xmmword ptr [rsp+78h+SystemTime.wYear]
0x18000f514  lea     rcx, [rdi+40h]; this
0x18000f518  lea     r8, [rsp+78h+var_58]; struct _SYSTEMTIME
0x18000f51d  movdqa  xmmword ptr [rsp+78h+var_58.wYear], xmm0
0x18000f523  mov     rdx, rbp; unsigned __int16 *
0x18000f526  call    ?AppendTimeEntry@CWdsMetadata@@QEAAKPEBGU_SYSTEMTIME@@@Z; CWdsMetadata::AppendTimeEntry(ushort const *,_SYSTEMTIME)
0x18000f52b  mov     r9d, 3E1h; unsigned int
0x18000f531  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f538  mov     ecx, eax; unsigned int
0x18000f53a  mov     edi, eax
0x18000f53c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f541  test    eax, eax
0x18000f543  jz      short loc_18000F553
0x18000f545  movzx   ebx, di
0x18000f548  or      ebx, 80070000h
0x18000f54e  test    edi, edi
0x18000f550  cmovle  ebx, edi
0x18000f553  mov     rcx, rsi; lpCriticalSection
0x18000f556  call    cs:__imp_LeaveCriticalSection
0x18000f55c  mov     eax, ebx
0x18000f55e  mov     rcx, [rsp+78h+var_38]
0x18000f563  xor     rcx, rsp; StackCookie
0x18000f566  call    __security_check_cookie
0x18000f56b  mov     rbx, [rsp+78h+arg_18]
0x18000f573  movaps  xmm6, [rsp+78h+var_28]
0x18000f578  add     rsp, 60h
0x18000f57c  pop     rdi
0x18000f57d  pop     rsi
0x18000f57e  pop     rbp
0x18000f57f  retn
```
