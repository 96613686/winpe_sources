# WppInitGlobalLogger

- ea: `0x140038afc`
- end: `0x140038dcf`
- name: `WppInitGlobalLogger`
- size: `723`
- prototype: `__int64 __fastcall(GUID *Guid)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140038fb0`

## callees

- `0x14000e660`
- `0x14001bc30`
- `0x14001bd10`
- `0x14001bd80`
- `0x140038afc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140038ba3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140038d5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140038ba3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140038d5a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140038bb4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140038d6b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140038bb4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140038d6b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140038bd9`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140038d8d`
- `ntoskrnl!RtlStringFromGUID` at `0x140038c93`
- `ntoskrnl!RtlStringFromGUID` at `0x140038c93`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140038cb0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140038d3a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140038cb0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140038d3a`

## string_xrefs

- `0x140038b72`: `RtlQueryRegistryValuesEx`
- `0x140038d49`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __fastcall WppInitGlobalLogger(GUID *Guid, _QWORD *a2, int *a3, _BYTE *a4)
{
  PVOID SystemRoutineAddress; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  PVOID v11; // rax
  int v12; // eax
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+3Ch] [rbp-C4h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+68h] [rbp-98h]
  const wchar_t *v21; // [rsp+70h] [rbp-90h]
  int *v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  int *v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  int v27; // [rsp+A0h] [rbp-60h]
  const wchar_t *v28; // [rsp+A8h] [rbp-58h]
  int *v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+B8h] [rbp-48h]
  int *v31; // [rsp+C0h] [rbp-40h]
  int v32; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  _OWORD v35[2]; // [rsp+110h] [rbp+10h] BYREF
  int v36; // [rsp+130h] [rbp+30h]

  v20 = 32;
  v15 = 0;
  v16 = 0;
  v21 = L"Start";
  v14 = 0;
  v22 = &v14;
  v13 = 0;
  v24 = &v13;
  v19 = 0;
  v23 = 4;
  v25 = 4;
  v26 = 0;
  GuidString = 0;
  v27 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  if ( ((int (__fastcall *)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))SystemRoutineAddress)(
         2147483650LL,
         L"WMI\\GlobalLogger\\",
         &v19,
         0,
         0) >= 0 )
  {
    if ( v14 )
    {
      v23 = 4;
      v21 = L"Flags";
      v25 = 4;
      v22 = &v15;
      v30 = 4;
      v24 = &v13;
      v19 = 0;
      v28 = L"Level";
      v29 = &v16;
      v31 = &v13;
      v36 = *(_DWORD *)L"\\";
      v20 = 32;
      v26 = 0;
      v27 = 32;
      v32 = 1;
      v33 = 0;
      v34 = 0;
      v35[0] = *(_OWORD *)L"WMI\\GlobalLogger\\";
      v35[1] = *(_OWORD *)L"alLogger\\";
      if ( !RtlStringFromGUID(Guid, &GuidString) )
      {
        if ( GuidString.Length <= 0x4Cu )
        {
          v9 = -1;
          v10 = -1;
          do
            ++v10;
          while ( *((_WORD *)v35 + v10) );
          memmove((char *)v35 + 2 * (unsigned int)v10, GuidString.Buffer + 1, GuidString.Length);
          do
            ++v9;
          while ( *((_WORD *)v35 + v9) );
          if ( 2 * (unsigned __int64)(unsigned int)(v9 - 1) >= 0x70 )
            _report_rangecheckfailure();
          *((_WORD *)v35 + (unsigned int)(v9 - 1)) = 0;
          RtlFreeUnicodeString(&GuidString);
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
          v11 = MmGetSystemRoutineAddress(&DestinationString);
          if ( !v11 )
            v11 = RtlQueryRegistryValues;
          if ( ((int (__fastcall *)(__int64, _OWORD *, __int64 *, _QWORD, _QWORD))v11)(2147483650LL, v35, &v19, 0, 0) >= 0
            && v14 == 1 )
          {
            v12 = v15 & 0x7FFFFFFF;
            *a2 = 1;
            *a3 = v12;
            *a4 = v16;
          }
        }
        else
        {
          RtlFreeUnicodeString(&GuidString);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140038afc  push    rbp
0x140038afe  push    rbx
0x140038aff  push    rsi
0x140038b00  push    rdi
0x140038b01  push    r12
0x140038b03  push    r14
0x140038b05  push    r15
0x140038b07  lea     rbp, [rsp-90h]
0x140038b0f  sub     rsp, 190h
0x140038b16  mov     rax, cs:__security_cookie
0x140038b1d  xor     rax, rsp
0x140038b20  mov     [rbp+0C0h+var_40], rax
0x140038b27  xor     r15d, r15d
0x140038b2a  mov     [rsp+1C0h+var_158], 20h ; ' '
0x140038b32  xorps   xmm0, xmm0
0x140038b35  mov     [rsp+1C0h+var_188], r15d
0x140038b3a  lea     rax, aStart
0x140038b41  mov     [rsp+1C0h+var_184], r15d
0x140038b46  mov     [rsp+1C0h+var_150], rax
0x140038b4b  mov     rdi, rdx
0x140038b4e  lea     rax, [rsp+1C0h+var_18C]
0x140038b53  mov     [rsp+1C0h+var_18C], r15d
0x140038b58  mov     [rsp+1C0h+var_148], rax
0x140038b5d  lea     r12d, [r15+4]
0x140038b61  lea     rax, [rsp+1C0h+var_190]
0x140038b66  mov     [rsp+1C0h+var_190], r15d
0x140038b6b  mov     rbx, rcx
0x140038b6e  mov     [rbp+0C0h+var_138], rax
0x140038b72  lea     rdx, SourceString
0x140038b79  mov     [rsp+1C0h+var_160], r15
0x140038b7e  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x140038b83  mov     [rbp+0C0h+var_140], r12d
0x140038b87  mov     r14, r9
0x140038b8a  mov     [rbp+0C0h+var_130], r12d
0x140038b8e  mov     rsi, r8
0x140038b91  mov     [rbp+0C0h+var_128], r15
0x140038b95  movups  xmmword ptr [rsp+1C0h+GuidString.Length], xmm0
0x140038b9a  mov     [rbp+0C0h+var_120], r15d
0x140038b9e  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x140038ba3  call    cs:__imp_RtlInitUnicodeString
0x140038baa  nop     dword ptr [rax+rax+00h]
0x140038baf  lea     rcx, [rsp+1C0h+DestinationString]; SystemRoutineName
0x140038bb4  call    cs:__imp_MmGetSystemRoutineAddress
0x140038bbb  nop     dword ptr [rax+rax+00h]
0x140038bc0  lea     r8, [rsp+1C0h+var_160]
0x140038bc5  mov     [rsp+1C0h+var_1A0], r15
0x140038bca  test    rax, rax
0x140038bcd  lea     rdx, aWmiGloballogge
0x140038bd4  mov     ecx, 80000002h
0x140038bd9  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140038be1  xor     r9d, r9d
0x140038be4  call    _guard_dispatch_icall
0x140038be9  test    eax, eax
0x140038beb  js      loc_140038CBC
0x140038bf1  cmp     [rsp+1C0h+var_18C], r15d
0x140038bf6  jz      loc_140038CBC
0x140038bfc  movups  xmm0, xmmword ptr cs:aWmiGloballogge
0x140038c03  lea     rax, aFlags
0x140038c0a  mov     [rbp+0C0h+var_140], r12d
0x140038c0e  movups  xmm1, xmmword ptr cs:aWmiGloballogge+10h
0x140038c15  mov     [rsp+1C0h+var_150], rax
0x140038c1a  lea     rdx, [rsp+1C0h+GuidString]; GuidString
0x140038c1f  lea     rax, [rsp+1C0h+var_188]
0x140038c24  mov     [rbp+0C0h+var_130], r12d
0x140038c28  mov     [rsp+1C0h+var_148], rax
0x140038c2d  mov     rcx, rbx; Guid
0x140038c30  lea     rax, [rsp+1C0h+var_190]
0x140038c35  mov     [rbp+0C0h+var_108], r12d
0x140038c39  mov     [rbp+0C0h+var_138], rax
0x140038c3d  lea     r12d, [r15+1]
0x140038c41  lea     rax, aLevel
0x140038c48  mov     [rsp+1C0h+var_160], r15
0x140038c4d  mov     [rbp+0C0h+var_118], rax
0x140038c51  lea     rax, [rsp+1C0h+var_184]
0x140038c56  mov     [rbp+0C0h+var_110], rax
0x140038c5a  lea     rax, [rsp+1C0h+var_190]
0x140038c5f  mov     [rbp+0C0h+var_100], rax
0x140038c63  mov     eax, dword ptr cs:aWmiGloballogge+20h
0x140038c69  mov     [rbp+0C0h+var_90], eax
0x140038c6c  mov     [rsp+1C0h+var_158], 20h ; ' '
0x140038c74  mov     [rbp+0C0h+var_128], r15
0x140038c78  mov     [rbp+0C0h+var_120], 20h ; ' '
0x140038c7f  mov     [rbp+0C0h+var_F8], r12d
0x140038c83  mov     [rbp+0C0h+var_F0], r15
0x140038c87  mov     [rbp+0C0h+var_E8], r15d
0x140038c8b  movaps  [rbp+0C0h+var_B0], xmm0
0x140038c8f  movaps  [rbp+0C0h+var_A0], xmm1
0x140038c93  call    cs:__imp_RtlStringFromGUID
0x140038c9a  nop     dword ptr [rax+rax+00h]
0x140038c9f  test    eax, eax
0x140038ca1  jnz     short loc_140038CBC
0x140038ca3  cmp     [rsp+1C0h+GuidString.Length], 4Ch ; 'L'
0x140038ca9  jbe     short loc_140038CDE
0x140038cab  lea     rcx, [rsp+1C0h+GuidString]; UnicodeString
0x140038cb0  call    cs:__imp_RtlFreeUnicodeString
0x140038cb7  nop     dword ptr [rax+rax+00h]
0x140038cbc  mov     rcx, [rbp+0C0h+var_40]
0x140038cc3  xor     rcx, rsp; StackCookie
0x140038cc6  call    __security_check_cookie
0x140038ccb  add     rsp, 190h
0x140038cd2  pop     r15
0x140038cd4  pop     r14
0x140038cd6  pop     r12
0x140038cd8  pop     rdi
0x140038cd9  pop     rsi
0x140038cda  pop     rbx
0x140038cdb  pop     rbp
0x140038cdc  retn
0x140038cde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140038ce2  lea     rcx, [rbp+0C0h+var_B0]
0x140038ce6  mov     rax, rbx
0x140038ce9  inc     rax
0x140038cec  cmp     [rcx+rax*2], r15w
0x140038cf1  jnz     short loc_140038CE9
0x140038cf3  mov     rdx, [rsp+1C0h+GuidString.Buffer]
0x140038cf8  lea     rcx, [rbp+0C0h+var_B0]
0x140038cfc  movzx   r8d, [rsp+1C0h+GuidString.Length]; Size
0x140038d02  add     rdx, 2; Src
0x140038d06  mov     eax, eax
0x140038d08  lea     rcx, [rcx+rax*2]; void *
0x140038d0c  call    memmove
0x140038d11  lea     rax, [rbp+0C0h+var_B0]
0x140038d15  inc     rbx
0x140038d18  cmp     [rax+rbx*2], r15w
0x140038d1d  jnz     short loc_140038D15
0x140038d1f  lea     ecx, [rbx-1]
0x140038d22  add     rcx, rcx
0x140038d25  cmp     rcx, 70h ; 'p'
0x140038d29  jnb     loc_140038DC9
0x140038d2f  mov     word ptr [rbp+rcx+0C0h+var_B0], r15w
0x140038d35  lea     rcx, [rsp+1C0h+GuidString]; UnicodeString
0x140038d3a  call    cs:__imp_RtlFreeUnicodeString
0x140038d41  nop     dword ptr [rax+rax+00h]
0x140038d46  xorps   xmm0, xmm0
0x140038d49  lea     rdx, SourceString
0x140038d50  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x140038d55  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x140038d5a  call    cs:__imp_RtlInitUnicodeString
0x140038d61  nop     dword ptr [rax+rax+00h]
0x140038d66  lea     rcx, [rsp+1C0h+DestinationString]; SystemRoutineName
0x140038d6b  call    cs:__imp_MmGetSystemRoutineAddress
0x140038d72  nop     dword ptr [rax+rax+00h]
0x140038d77  lea     r8, [rsp+1C0h+var_160]
0x140038d7c  mov     [rsp+1C0h+var_1A0], r15
0x140038d81  test    rax, rax
0x140038d84  lea     rdx, [rbp+0C0h+var_B0]
0x140038d88  mov     ecx, 80000002h
0x140038d8d  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140038d95  xor     r9d, r9d
0x140038d98  call    _guard_dispatch_icall
0x140038d9d  test    eax, eax
0x140038d9f  js      loc_140038CBC
0x140038da5  cmp     [rsp+1C0h+var_18C], r12d
0x140038daa  jnz     loc_140038CBC
0x140038db0  mov     eax, [rsp+1C0h+var_188]
0x140038db4  btr     eax, 1Fh
0x140038db8  mov     [rdi], r12
0x140038dbb  mov     [rsi], eax
0x140038dbd  mov     al, byte ptr [rsp+1C0h+var_184]
0x140038dc1  mov     [r14], al
0x140038dc4  jmp     loc_140038CBC
0x140038dc9  call    __report_rangecheckfailure
```
