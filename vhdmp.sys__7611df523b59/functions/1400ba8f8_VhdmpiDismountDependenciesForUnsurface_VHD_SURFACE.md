# VhdmpiDismountDependenciesForUnsurface(_VHD_SURFACE *)

- ea: `0x1400ba8f8`
- end: `0x1400bab4b`
- name: `?VhdmpiDismountDependenciesForUnsurface@@YAXPEAU_VHD_SURFACE@@@Z`
- size: `595`
- prototype: `void __fastcall(struct _VHD_SURFACE *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400bbd64`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x14001b7fc`
- `0x14001bc68`
- `0x14001dbb4`
- `0x140023560`
- `0x140035e94`
- `0x14005d7c0`
- `0x1400ba8f8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400ba962`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400ba962`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400bab19`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400bab19`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ba980`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ba980`
- `FSDEPENDS!DependentFSDismountForUnsurface` at `0x1400baa0b`
- `FSDEPENDS!DependentFSDismountForUnsurface` at `0x1400baa0b`

## string_xrefs

- `0x1400baaf3`: `Vhdmpi: returned 0x%x from DependentFSDismountForUnsurface for disk %p`
- `0x1400baafa`: `VhdmpiDismountDependenciesForUnsurface`

## pseudocode

```c
void __fastcall VhdmpiDismountDependenciesForUnsurface(struct _VHD_SURFACE *a1)
{
  int v2; // eax
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // r8
  int *v6; // rsi
  __int64 v7; // rcx
  const wchar_t *v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // edx
  const wchar_t *v13; // [rsp+40h] [rbp-30h] BYREF
  int *v14; // [rsp+48h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-20h] BYREF
  const GUID *v16; // [rsp+60h] [rbp-10h]

  if ( *((_QWORD *)a1 + 37) )
  {
    v2 = *((_DWORD *)a1 + 14);
    if ( (v2 & 0x200) == 0 && (v2 & 0x40) == 0 )
    {
      v3 = *((_QWORD *)a1 + 2);
      ActivityId = 0;
      v16 = 0;
      ExAcquirePushLockSharedEx(v3 + 896, 0);
      VhdmpiAcquirePassiveLock(v3 + 112, v4, v5);
      EtwActivityIdControl(3u, &ActivityId);
      v6 = (int *)L"Unknown";
      v16 = 0;
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
      {
        v7 = *(_QWORD *)(*(_QWORD *)(v3 + 144) + 120LL);
        v8 = L"Unknown";
        if ( v7 )
          v8 = *(const wchar_t **)(*(_QWORD *)(v3 + 144) + 120LL);
        v13 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&dword_14007D8CC,
          (__int64)&ActivityId,
          0,
          &v13);
      }
      v9 = DependentFSDismountForUnsurface(
             *((_QWORD *)a1 + 37),
             0,
             *(_QWORD *)(v3 + 144),
             *(_QWORD *)(*(_QWORD *)(v3 + 144) + 1040LL));
      if ( v9 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
      {
        LODWORD(v13) = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
      }
      if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
      {
        v10 = *(_QWORD *)(v3 + 144);
        LODWORD(v13) = v9;
        v11 = *(_QWORD *)(v10 + 120);
        if ( v11 )
          v6 = *(int **)(v10 + 120);
        v14 = v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v11,
          (unsigned __int8 *)byte_14007D85D,
          &ActivityId,
          v16,
          &v14,
          (__int64)&v13);
      }
      if ( v9 < 0 && (unsigned int)dword_140087708 > 2 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          TraceEvents(
            (int)"VhdmpiDismountDependenciesForUnsurface",
            525,
            v12 - 14,
            v12,
            "Vhdmpi: returned 0x%x from DependentFSDismountForUnsurface for disk %p",
            v9);
      }
      VhdmpiReleasePassiveLock(v3 + 112);
      ExReleasePushLockSharedEx(v3 + 896, 0);
    }
  }
}

```

## disassembly

```asm
0x1400ba8f8  mov     [rsp-28h+arg_8], rbx
0x1400ba8fd  mov     [rsp-28h+arg_10], rsi
0x1400ba902  push    rbp
0x1400ba903  push    rdi
0x1400ba904  push    r12
0x1400ba906  push    r14
0x1400ba908  push    r15
0x1400ba90a  mov     rbp, rsp
0x1400ba90d  sub     rsp, 70h
0x1400ba911  mov     rax, cs:__security_cookie
0x1400ba918  xor     rax, rsp
0x1400ba91b  mov     [rbp+var_8], rax
0x1400ba91f  cmp     qword ptr [rcx+128h], 0
0x1400ba927  mov     rbx, rcx
0x1400ba92a  jz      loc_1400BAB25
0x1400ba930  mov     eax, [rcx+38h]
0x1400ba933  bt      eax, 9
0x1400ba937  jb      loc_1400BAB25
0x1400ba93d  test    al, 40h
0x1400ba93f  jnz     loc_1400BAB25
0x1400ba945  mov     rdi, [rcx+10h]
0x1400ba949  xorps   xmm0, xmm0
0x1400ba94c  xor     eax, eax
0x1400ba94e  xor     edx, edx
0x1400ba950  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1400ba954  mov     [rbp+var_10], rax
0x1400ba958  lea     r14, [rdi+380h]
0x1400ba95f  mov     rcx, r14
0x1400ba962  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400ba969  nop     dword ptr [rax+rax+00h]
0x1400ba96e  lea     rcx, [rdi+70h]
0x1400ba972  call    VhdmpiAcquirePassiveLock
0x1400ba977  lea     rdx, [rbp+ActivityId]; ActivityId
0x1400ba97b  mov     ecx, 3; ControlCode
0x1400ba980  call    cs:__imp_EtwActivityIdControl
0x1400ba987  nop     dword ptr [rax+rax+00h]
0x1400ba98c  mov     eax, cs:dword_1400876D0
0x1400ba992  lea     rsi, aUnknown; "Unknown"
0x1400ba999  mov     [rbp+var_10], 0
0x1400ba9a1  mov     r12d, 10000h
0x1400ba9a7  cmp     eax, 4
0x1400ba9aa  jbe     short loc_1400BA9F4
0x1400ba9ac  mov     edx, r12d
0x1400ba9af  lea     rcx, dword_1400876D0
0x1400ba9b6  call    _tlgKeywordOn
0x1400ba9bb  test    al, al
0x1400ba9bd  jz      short loc_1400BA9F4
0x1400ba9bf  mov     rax, [rdi+90h]
0x1400ba9c6  lea     r8, [rbp+ActivityId]
0x1400ba9ca  lea     rdx, dword_14007D8CC
0x1400ba9d1  mov     rcx, [rax+78h]
0x1400ba9d5  mov     rax, rsi
0x1400ba9d8  test    rcx, rcx
0x1400ba9db  cmovnz  rax, rcx
0x1400ba9df  xor     r9d, r9d
0x1400ba9e2  mov     [rbp+var_30], rax
0x1400ba9e6  lea     rax, [rbp+var_30]
0x1400ba9ea  mov     [rsp+70h+var_50], rax
0x1400ba9ef  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1400ba9f4  mov     r8, [rdi+90h]
0x1400ba9fb  xor     edx, edx
0x1400ba9fd  mov     rcx, [rbx+128h]
0x1400baa04  mov     r9, [r8+410h]
0x1400baa0b  call    cs:__imp_DependentFSDismountForUnsurface
0x1400baa12  nop     dword ptr [rax+rax+00h]
0x1400baa17  mov     ebx, eax
0x1400baa19  test    eax, eax
0x1400baa1b  jns     short loc_1400BAA5B
0x1400baa1d  mov     ecx, cs:dword_1400876D0
0x1400baa23  cmp     ecx, 2
0x1400baa26  jbe     short loc_1400BAA5B
0x1400baa28  mov     rdx, r12
0x1400baa2b  lea     rcx, dword_1400876D0
0x1400baa32  call    _tlgKeywordOn
0x1400baa37  test    al, al
0x1400baa39  jz      short loc_1400BAA5B
0x1400baa3b  mov     r9, [rbp+var_10]
0x1400baa3f  lea     rax, [rbp+var_30]
0x1400baa43  lea     r8, [rbp+ActivityId]
0x1400baa47  mov     [rsp+70h+var_50], rax
0x1400baa4c  lea     rdx, dword_14007D8A4
0x1400baa53  mov     dword ptr [rbp+var_30], ebx
0x1400baa56  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400baa5b  mov     eax, cs:dword_1400876D0
0x1400baa61  cmp     eax, 4
0x1400baa64  jbe     short loc_1400BAAB8
0x1400baa66  mov     rdx, r12
0x1400baa69  lea     rcx, dword_1400876D0
0x1400baa70  call    _tlgKeywordOn
0x1400baa75  test    al, al
0x1400baa77  jz      short loc_1400BAAB8
0x1400baa79  mov     rax, [rdi+90h]
0x1400baa80  lea     r8, [rbp+ActivityId]
0x1400baa84  mov     r9, [rbp+var_10]
0x1400baa88  lea     rdx, byte_14007D85D
0x1400baa8f  mov     dword ptr [rbp+var_30], ebx
0x1400baa92  mov     rcx, [rax+78h]
0x1400baa96  lea     rax, [rbp+var_30]
0x1400baa9a  mov     qword ptr [rsp+70h+var_48], rax
0x1400baa9f  test    rcx, rcx
0x1400baaa2  lea     rax, [rbp+var_28]
0x1400baaa6  cmovnz  rsi, rcx
0x1400baaaa  mov     [rsp+70h+var_50], rax
0x1400baaaf  mov     [rbp+var_28], rsi
0x1400baab3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400baab8  test    ebx, ebx
0x1400baaba  jns     short loc_1400BAB0B
0x1400baabc  mov     eax, cs:dword_140087708
0x1400baac2  cmp     eax, 2
0x1400baac5  jbe     short loc_1400BAB0B
0x1400baac7  mov     edx, 10h
0x1400baacc  lea     rcx, dword_140087708
0x1400baad3  call    _tlgKeywordOn
0x1400baad8  test    al, al
0x1400baada  jz      short loc_1400BAB0B
0x1400baadc  mov     ecx, 20Dh
0x1400baae1  mov     [rsp+70h+var_40], rdi
0x1400baae6  mov     r9d, edx; int
0x1400baae9  mov     dword ptr [rsp+70h+var_48], ebx; char
0x1400baaed  lea     r8d, [rdx-0Eh]; int
0x1400baaf1  mov     edx, ecx; int
0x1400baaf3  lea     rax, aVhdmpiReturned; "Vhdmpi: returned 0x%x from DependentFSD"...
0x1400baafa  lea     rcx, aVhdmpidismount; "VhdmpiDismountDependenciesForUnsurface"
0x1400bab01  mov     [rsp+70h+var_50], rax; char *
0x1400bab06  call    TraceEvents
0x1400bab0b  lea     rcx, [rdi+70h]
0x1400bab0f  call    VhdmpiReleasePassiveLock
0x1400bab14  xor     edx, edx
0x1400bab16  mov     rcx, r14
0x1400bab19  call    cs:__imp_ExReleasePushLockSharedEx
0x1400bab20  nop     dword ptr [rax+rax+00h]
0x1400bab25  mov     rcx, [rbp+var_8]
0x1400bab29  xor     rcx, rsp; StackCookie
0x1400bab2c  call    __security_check_cookie
0x1400bab31  lea     r11, [rsp+70h+var_s0]
0x1400bab36  mov     rbx, [r11+38h]
0x1400bab3a  mov     rsi, [r11+40h]
0x1400bab3e  mov     rsp, r11
0x1400bab41  pop     r15
0x1400bab43  pop     r14
0x1400bab45  pop     r12
0x1400bab47  pop     rdi
0x1400bab48  pop     rbp
0x1400bab49  retn
```
