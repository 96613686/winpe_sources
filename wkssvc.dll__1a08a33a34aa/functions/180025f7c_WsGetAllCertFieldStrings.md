# WsGetAllCertFieldStrings

- ea: `0x180025f7c`
- end: `0x180026219`
- name: `WsGetAllCertFieldStrings`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800222ec`

## callees

- `0x18001dcac`
- `0x180024550`
- `0x180025f7c`
- `0x180026220`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800261b4`
- `ntdll!RtlNtStatusToDosError` at `0x1800261b4`
- `ntdll!RtlUnicodeStringToInteger` at `0x180026143`
- `ntdll!RtlUnicodeStringToInteger` at `0x180026143`
- `ntdll!RtlInitUnicodeString` at `0x1800260d0`
- `ntdll!RtlInitUnicodeString` at `0x1800260d0`
- `ntdll!RtlFreeUnicodeString` at `0x180026157`
- `ntdll!RtlFreeUnicodeString` at `0x180026157`

## string_xrefs

- `0x180026053`: `StoreName`

## pseudocode

```c
__int64 __fastcall WsGetAllCertFieldStrings(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int CertFieldString; // esi
  unsigned __int16 v6; // di
  const WCHAR *v7; // r15
  __int64 v8; // rcx
  char v9; // r14
  WCHAR **v10; // r9
  __int64 v11; // rcx
  int v12; // r14d
  UNICODE_STRING String; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR SourceString; // [rsp+40h] [rbp-C0h]
  _BYTE v17[8]; // [rsp+48h] [rbp-B8h]
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h]
  char v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  const WCHAR *v21; // [rsp+70h] [rbp-90h]
  char v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  const WCHAR *v24; // [rsp+88h] [rbp-78h]
  char v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  const WCHAR *v27; // [rsp+A0h] [rbp-60h]
  char v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  const WCHAR *v30; // [rsp+B8h] [rbp-48h]
  char v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  const WCHAR *v33; // [rsp+D0h] [rbp-30h]
  char v34; // [rsp+D8h] [rbp-28h]
  __int64 v35; // [rsp+E0h] [rbp-20h]
  const WCHAR *v36; // [rsp+E8h] [rbp-18h]
  char v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  const WCHAR *v39; // [rsp+100h] [rbp+0h]
  char v40; // [rsp+108h] [rbp+8h]
  __int64 v41; // [rsp+110h] [rbp+10h]
  const WCHAR *v42; // [rsp+118h] [rbp+18h]
  char v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+128h] [rbp+28h]
  __int64 Value; // [rsp+170h] [rbp+70h] BYREF
  WCHAR *v46; // [rsp+180h] [rbp+80h] BYREF

  Value = a1;
  v3 = *a3;
  SourceString = L"Subject";
  v46 = 0;
  LODWORD(Value) = 0;
  v17[0] = 0;
  v18[0] = v3 + 8;
  CertFieldString = 0;
  v19 = 0;
  v18[1] = L"Issuer";
  v6 = 0;
  v22 = 0;
  v20 = v3 + 16;
  v21 = L"ThumbPrint";
  v23 = v3 + 24;
  v24 = L"FriendlyName";
  v26 = v3 + 32;
  v27 = L"NotBefore";
  v29 = v3 + 40;
  v30 = L"NotAfter";
  v32 = v3 + 48;
  v33 = L"StoreLocation";
  v35 = v3 + 56;
  v36 = L"StoreName";
  v38 = v3 + 64;
  v39 = L"Type";
  v41 = v3 + 80;
  v42 = L"Flags";
  v44 = v3 + 84;
  DestinationString = 0;
  v25 = 0;
  String = 0;
  v28 = 0;
  v31 = 0;
  v34 = 0;
  v37 = 0;
  v40 = 1;
  v43 = 1;
  while ( v6 < 0xAu )
  {
    v7 = *(const WCHAR **)&v17[24 * v6 - 8];
    RtlInitUnicodeString(&DestinationString, v7);
    v9 = v17[24 * v6];
    v10 = &v46;
    if ( !v9 )
      v10 = (WCHAR **)v18[3 * v6];
    CertFieldString = WsGetCertFieldString(v8, a2, &DestinationString, v10);
    if ( CertFieldString )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v7);
      }
      return CertFieldString;
    }
    if ( v9 )
    {
      v11 = -1;
      String.Buffer = v46;
      do
        ++v11;
      while ( v46[v11] );
      String.MaximumLength = 2 * (v11 + 1);
      String.Length = String.MaximumLength;
      v12 = RtlUnicodeStringToInteger(&String, 0, (PULONG)&Value);
      RtlFreeUnicodeString(&String);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
            (unsigned int)v12);
        }
        return RtlNtStatusToDosError(v12);
      }
      *(_DWORD *)v18[3 * v6] = Value;
    }
    ++v6;
  }
  return CertFieldString;
}

```

## disassembly

```asm
0x180025f7c  mov     [rsp-8+arg_8], rbx
0x180025f81  mov     [rsp-8+Value], rcx
0x180025f86  push    rbp
0x180025f87  push    rsi
0x180025f88  push    rdi
0x180025f89  push    r12
0x180025f8b  push    r13
0x180025f8d  push    r14
0x180025f8f  push    r15
0x180025f91  lea     rbp, [rsp-30h]
0x180025f96  sub     rsp, 130h
0x180025f9d  mov     rcx, [r8]
0x180025fa0  lea     rax, aSubject; "Subject"
0x180025fa7  mov     [rsp+160h+SourceString], rax
0x180025fac  xor     r13d, r13d
0x180025faf  xorps   xmm0, xmm0
0x180025fb2  mov     [rbp+60h+arg_10], r13
0x180025fb9  mov     r12, rdx
0x180025fbc  mov     dword ptr [rbp+60h+Value], r13d
0x180025fc0  lea     rax, [rcx+8]
0x180025fc4  mov     [rsp+160h+var_118], r13b
0x180025fc9  mov     [rsp+160h+var_110], rax
0x180025fce  mov     esi, r13d
0x180025fd1  lea     rax, aIssuer; "Issuer"
0x180025fd8  mov     [rsp+160h+var_100], r13b
0x180025fdd  mov     [rsp+160h+var_108], rax
0x180025fe2  mov     edi, r13d
0x180025fe5  lea     rax, [rcx+10h]
0x180025fe9  mov     [rsp+160h+var_E8], r13b
0x180025fee  mov     [rsp+160h+var_F8], rax
0x180025ff3  lea     rax, aThumbprint; "ThumbPrint"
0x180025ffa  mov     [rsp+160h+var_F0], rax
0x180025fff  lea     rax, [rcx+18h]
0x180026003  mov     [rbp+60h+var_E0], rax
0x180026007  lea     rax, aFriendlyname; "FriendlyName"
0x18002600e  mov     [rbp+60h+var_D8], rax
0x180026012  lea     rax, [rcx+20h]
0x180026016  mov     [rbp+60h+var_C8], rax
0x18002601a  lea     rax, aNotbefore; "NotBefore"
0x180026021  mov     [rbp+60h+var_C0], rax
0x180026025  lea     rax, [rcx+28h]
0x180026029  mov     [rbp+60h+var_B0], rax
0x18002602d  lea     rax, aNotafter; "NotAfter"
0x180026034  mov     [rbp+60h+var_A8], rax
0x180026038  lea     rax, [rcx+30h]
0x18002603c  mov     [rbp+60h+var_98], rax
0x180026040  lea     rax, aStorelocation; "StoreLocation"
0x180026047  mov     [rbp+60h+var_90], rax
0x18002604b  lea     rax, [rcx+38h]
0x18002604f  mov     [rbp+60h+var_80], rax
0x180026053  lea     rax, aStorename; "StoreName"
0x18002605a  mov     [rbp+60h+var_78], rax
0x18002605e  lea     rax, [rcx+40h]
0x180026062  mov     [rbp+60h+var_68], rax
0x180026066  lea     rax, aType; "Type"
0x18002606d  mov     [rbp+60h+var_60], rax
0x180026071  lea     rax, [rcx+50h]
0x180026075  mov     [rbp+60h+var_50], rax
0x180026079  lea     rax, aFlags; "Flags"
0x180026080  mov     [rbp+60h+var_48], rax
0x180026084  lea     rax, [rcx+54h]
0x180026088  mov     [rbp+60h+var_38], rax
0x18002608c  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x180026091  mov     [rbp+60h+var_D0], r13b
0x180026095  movups  xmmword ptr [rsp+160h+String.Length], xmm0
0x18002609a  mov     [rbp+60h+var_B8], r13b
0x18002609e  mov     [rbp+60h+var_A0], r13b
0x1800260a2  mov     [rbp+60h+var_88], r13b
0x1800260a6  mov     [rbp+60h+var_70], r13b
0x1800260aa  mov     [rbp+60h+var_58], 1
0x1800260ae  mov     [rbp+60h+var_40], 1
0x1800260b2  cmp     di, 0Ah
0x1800260b6  jnb     loc_1800261FB
0x1800260bc  movzx   eax, di
0x1800260bf  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1800260c4  lea     rbx, [rax+rax*2]
0x1800260c8  mov     r15, [rsp+rbx*8+160h+SourceString]
0x1800260cd  mov     rdx, r15; SourceString
0x1800260d0  call    cs:__imp_RtlInitUnicodeString
0x1800260d7  nop     dword ptr [rax+rax+00h]
0x1800260dc  mov     r14b, [rsp+rbx*8+160h+var_118]
0x1800260e1  lea     r9, [rbp+60h+arg_10]
0x1800260e8  test    r14b, r14b
0x1800260eb  jnz     short loc_1800260F2
0x1800260ed  mov     r9, [rsp+rbx*8+160h+var_110]
0x1800260f2  lea     r8, [rsp+160h+DestinationString]
0x1800260f7  mov     rdx, r12
0x1800260fa  call    WsGetCertFieldString
0x1800260ff  mov     esi, eax
0x180026101  test    eax, eax
0x180026103  jnz     loc_1800261C4
0x180026109  test    r14b, r14b
0x18002610c  jz      short loc_180026172
0x18002610e  mov     rax, [rbp+60h+arg_10]
0x180026115  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026119  mov     [rsp+160h+String.Buffer], rax
0x18002611e  inc     rcx
0x180026121  cmp     [rax+rcx*2], r13w
0x180026126  jnz     short loc_18002611E
0x180026128  inc     cx
0x18002612b  lea     r8, [rbp+60h+Value]; Value
0x18002612f  add     cx, cx
0x180026132  xor     edx, edx; Base
0x180026134  mov     [rsp+160h+String.MaximumLength], cx
0x180026139  mov     [rsp+160h+String.Length], cx
0x18002613e  lea     rcx, [rsp+160h+String]; String
0x180026143  call    cs:__imp_RtlUnicodeStringToInteger
0x18002614a  nop     dword ptr [rax+rax+00h]
0x18002614f  lea     rcx, [rsp+160h+String]; UnicodeString
0x180026154  mov     r14d, eax
0x180026157  call    cs:__imp_RtlFreeUnicodeString
0x18002615e  nop     dword ptr [rax+rax+00h]
0x180026163  test    r14d, r14d
0x180026166  js      short loc_18002617A
0x180026168  mov     rcx, [rsp+rbx*8+160h+var_110]
0x18002616d  mov     eax, dword ptr [rbp+60h+Value]
0x180026170  mov     [rcx], eax
0x180026172  inc     di
0x180026175  jmp     loc_1800260B2
0x18002617a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026181  lea     rax, WPP_GLOBAL_Control
0x180026188  cmp     rcx, rax
0x18002618b  jz      short loc_1800261B1
0x18002618d  test    byte ptr [rcx+1Ch], 2
0x180026191  jz      short loc_1800261B1
0x180026193  cmp     byte ptr [rcx+19h], 1
0x180026197  jb      short loc_1800261B1
0x180026199  mov     rcx, [rcx+10h]
0x18002619d  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x1800261a4  mov     edx, 0Fh
0x1800261a9  mov     r9d, r14d
0x1800261ac  call    WPP_SF_d
0x1800261b1  mov     ecx, r14d; Status
0x1800261b4  call    cs:__imp_RtlNtStatusToDosError
0x1800261bb  nop     dword ptr [rax+rax+00h]
0x1800261c0  mov     esi, eax
0x1800261c2  jmp     short loc_1800261FB
0x1800261c4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800261cb  lea     rax, WPP_GLOBAL_Control
0x1800261d2  cmp     rcx, rax
0x1800261d5  jz      short loc_1800261FB
0x1800261d7  test    byte ptr [rcx+1Ch], 2
0x1800261db  jz      short loc_1800261FB
0x1800261dd  cmp     byte ptr [rcx+19h], 1
0x1800261e1  jb      short loc_1800261FB
0x1800261e3  mov     rcx, [rcx+10h]
0x1800261e7  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x1800261ee  mov     edx, 0Eh
0x1800261f3  mov     r9, r15
0x1800261f6  call    WPP_SF_S
0x1800261fb  mov     rbx, [rsp+160h+arg_8]
0x180026203  mov     eax, esi
0x180026205  add     rsp, 130h
0x18002620c  pop     r15
0x18002620e  pop     r14
0x180026210  pop     r13
0x180026212  pop     r12
0x180026214  pop     rdi
0x180026215  pop     rsi
0x180026216  pop     rbp
0x180026217  retn
```
