# W3WP_HOST::CheckConfigFile(void)

- ea: `0x180003684`
- end: `0x180003816`
- name: `?CheckConfigFile@W3WP_HOST@@QEAAJXZ`
- size: `402`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800061dc`
- `0x18000b670`

## callees

- `0x180003684`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `msvcrt!_ultow` at `0x180003783`
- `msvcrt!_ultow` at `0x180003783`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800037bb`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800037bb`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::CheckConfigFile(W3WP_HOST *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v8; // [rsp+48h] [rbp-9h] BYREF
  unsigned int Value; // [rsp+50h] [rbp-1h] BYREF
  __int64 v10; // [rsp+58h] [rbp+7h] BYREF
  __int128 v11; // [rsp+60h] [rbp+Fh] BYREF
  __int128 v12; // [rsp+70h] [rbp+1Fh] BYREF
  wchar_t Buffer[16]; // [rsp+80h] [rbp+2Fh] BYREF

  v10 = 0;
  v2 = *((_QWORD *)this + 24);
  v8 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v2 + 24LL))(
         v2,
         L"system.applicationHost/sites",
         L"MACHINE/WEBROOT/APPHOST",
         &v10,
         &v8,
         0);
  if ( v3 < 0 )
  {
    v4 = *((_QWORD *)this + 39);
    v5 = 0;
    v11 = 0;
    Value = 0;
    v12 = 0;
    *(_QWORD *)&v11 = *(_QWORD *)(v4 + 24);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v8 + 24LL))(v8, (char *)&v11 + 8);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v8 + 40LL))(v8, &v12);
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 32LL))(v8, &Value);
      v5 = Value;
    }
    else
    {
      *((_QWORD *)&v11 + 1) = L"Unknown Error";
      *(_QWORD *)&v12 = L"Unknown File";
    }
    _ultow(v5, Buffer, 10);
    *((_QWORD *)&v12 + 1) = Buffer;
    v6 = (unsigned __int16)v3;
    if ( (v3 & 0x1FFF0000) != 0x70000 )
      v6 = v3;
    EVENT_LOG::LogEvent((W3WP_HOST *)((char *)this + 80), 0xC0000903, 4u, (const unsigned __int16 **const)&v11, v6);
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003684  mov     r11, rsp
0x180003687  mov     [r11+10h], rbx
0x18000368b  mov     [r11+18h], rdi
0x18000368f  push    rbp
0x180003690  lea     rbp, [r11-5Fh]
0x180003694  sub     rsp, 0A0h
0x18000369b  mov     rax, cs:__security_cookie
0x1800036a2  xor     rax, rsp
0x1800036a5  mov     [rbp+57h+var_8], rax
0x1800036a9  mov     rdi, rcx
0x1800036ac  mov     [rbp+57h+var_50], 0
0x1800036b4  mov     rcx, [rcx+0C0h]
0x1800036bb  lea     rdx, [rbp+57h+var_60]
0x1800036bf  mov     [rbp+57h+var_60], 0
0x1800036c7  lea     r9, [rbp+57h+var_50]
0x1800036cb  mov     qword ptr [r11-80h], 0
0x1800036d3  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800036da  mov     [rsp+0A0h+var_80], rdx
0x1800036df  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x1800036e6  mov     rax, [rcx]
0x1800036e9  mov     rax, [rax+18h]
0x1800036ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f2  mov     ebx, eax
0x1800036f4  test    eax, eax
0x1800036f6  jns     loc_1800037C1
0x1800036fc  mov     rcx, [rdi+138h]
0x180003703  xorps   xmm0, xmm0
0x180003706  xor     eax, eax
0x180003708  movups  [rbp+57h+var_48], xmm0
0x18000370c  mov     [rbp+57h+Value], eax
0x18000370f  movups  [rbp+57h+var_38], xmm0
0x180003713  mov     rdx, [rcx+18h]
0x180003717  mov     rcx, [rbp+57h+var_60]
0x18000371b  mov     qword ptr [rbp+57h+var_48], rdx
0x18000371f  test    rcx, rcx
0x180003722  jz      short loc_180003761
0x180003724  mov     rax, [rcx]
0x180003727  lea     rdx, [rbp+57h+var_48+8]
0x18000372b  mov     rax, [rax+18h]
0x18000372f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003734  mov     rcx, [rbp+57h+var_60]
0x180003738  lea     rdx, [rbp+57h+var_38]
0x18000373c  mov     rax, [rcx]
0x18000373f  mov     rax, [rax+28h]
0x180003743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003748  mov     rcx, [rbp+57h+var_60]
0x18000374c  lea     rdx, [rbp+57h+Value]
0x180003750  mov     rax, [rcx]
0x180003753  mov     rax, [rax+20h]
0x180003757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375c  mov     eax, [rbp+57h+Value]
0x18000375f  jmp     short loc_180003777
0x180003761  lea     rcx, aUnknownError; "Unknown Error"
0x180003768  mov     qword ptr [rbp+57h+var_48+8], rcx
0x18000376c  lea     rcx, aUnknownFile; "Unknown File"
0x180003773  mov     qword ptr [rbp+57h+var_38], rcx
0x180003777  mov     r8d, 0Ah; Radix
0x18000377d  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180003781  mov     ecx, eax; Value
0x180003783  call    cs:__imp__ultow
0x180003789  lea     rax, [rbp+57h+Buffer]
0x18000378d  mov     qword ptr [rbp+57h+var_38+8], rax
0x180003791  mov     eax, ebx
0x180003793  and     eax, 1FFF0000h
0x180003798  cmp     eax, 70000h
0x18000379d  movzx   eax, bx
0x1800037a0  jz      short loc_1800037A4
0x1800037a2  mov     eax, ebx
0x1800037a4  mov     r8d, 4
0x1800037aa  mov     dword ptr [rsp+0A0h+var_80], eax
0x1800037ae  lea     rcx, [rdi+50h]
0x1800037b2  mov     edx, 0C0000903h
0x1800037b7  lea     r9, [rbp+57h+var_48]
0x1800037bb  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800037c1  mov     rcx, [rbp+57h+var_60]
0x1800037c5  test    rcx, rcx
0x1800037c8  jz      short loc_1800037DE
0x1800037ca  mov     rax, [rcx]
0x1800037cd  mov     rax, [rax+10h]
0x1800037d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d6  mov     [rbp+57h+var_60], 0
0x1800037de  mov     rcx, [rbp+57h+var_50]
0x1800037e2  test    rcx, rcx
0x1800037e5  jz      short loc_1800037F3
0x1800037e7  mov     rax, [rcx]
0x1800037ea  mov     rax, [rax+10h]
0x1800037ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f3  mov     eax, ebx
0x1800037f5  mov     rcx, [rbp+57h+var_8]
0x1800037f9  xor     rcx, rsp; StackCookie
0x1800037fc  call    __security_check_cookie
0x180003801  lea     r11, [rsp+0A0h+var_s0]
0x180003809  mov     rbx, [r11+18h]
0x18000380d  mov     rdi, [r11+20h]
0x180003811  mov     rsp, r11
0x180003814  pop     rbp
0x180003815  retn
```
