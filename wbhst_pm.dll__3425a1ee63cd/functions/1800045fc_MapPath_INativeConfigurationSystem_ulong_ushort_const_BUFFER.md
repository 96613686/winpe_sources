# MapPath(INativeConfigurationSystem *,ulong,ushort const *,BUFFER *)

- ea: `0x1800045fc`
- end: `0x180004797`
- name: `?MapPath@@YAJPEAVINativeConfigurationSystem@@KPEBGPEAVBUFFER@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct INativeConfigurationSystem *, unsigned int, const unsigned __int16 *, struct BUFFER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800038f0`
- `0x180003fa0`

## callees

- `0x1800042e0`
- `0x1800045fc`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046f4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004668`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004775`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004668`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004775`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800046ea`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800046ea`

## pseudocode

```c
__int64 __fastcall MapPath(
        struct INativeConfigurationSystem *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct BUFFER *a4)
{
  int ApplicationSiteName; // esi
  signed int v9; // ebx
  __int64 v10; // r9
  signed int LastError; // eax
  __int64 v12; // r9
  int v13; // [rsp+50h] [rbp-39h] BYREF
  __int64 v14; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp-29h] BYREF
  _OWORD *v16; // [rsp+80h] [rbp-9h]
  int v17; // [rsp+88h] [rbp-1h]
  __int16 v18; // [rsp+8Ch] [rbp+3h]
  _OWORD v19[2]; // [rsp+90h] [rbp+7h] BYREF

  v17 = 32;
  v18 = 256;
  v13 = 0;
  v16 = v19;
  memset(v19, 0, sizeof(v19));
  v14 = 0;
  ApplicationSiteName = GetApplicationSiteName(a1, a2, (struct BUFFER *)v15);
  if ( ApplicationSiteName >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64 *))(*(_QWORD *)a1 + 56LL))(a1, &v14);
    if ( v9 >= 0 )
    {
      v10 = *((_QWORD *)a4 + 4);
      v13 = *((_DWORD *)a4 + 10) >> 1;
      v9 = (*(__int64 (__fastcall **)(__int64, _OWORD *, const unsigned __int16 *, __int64, int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v14 + 40LL))(
             v14,
             v16,
             a3,
             v10,
             &v13,
             0,
             0,
             0);
      if ( v9 == -2147024774 )
      {
        if ( BUFFER::Resize(a4, 2 * v13) )
        {
          v12 = *((_QWORD *)a4 + 4);
          v13 = *((_DWORD *)a4 + 10) >> 1;
          v9 = (*(__int64 (__fastcall **)(__int64, _OWORD *, const unsigned __int16 *, __int64, int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v14 + 40LL))(
                 v14,
                 v16,
                 a3,
                 v12,
                 &v13,
                 0,
                 0,
                 0);
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    BUFFER::~BUFFER((BUFFER *)v15);
    return (unsigned int)v9;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)v15);
    return (unsigned int)ApplicationSiteName;
  }
}

```

## disassembly

```asm
0x1800045fc  push    rbp
0x1800045fe  push    rbx
0x1800045ff  push    rsi
0x180004600  push    rdi
0x180004601  push    r14
0x180004603  lea     rbp, [rsp-37h]
0x180004608  sub     rsp, 0C0h
0x18000460f  mov     rax, cs:__security_cookie
0x180004616  xor     rax, rsp
0x180004619  mov     [rbp+57h+var_30], rax
0x18000461d  xorps   xmm0, xmm0
0x180004620  mov     [rbp+57h+var_58], 20h ; ' '
0x180004627  mov     r14, r8
0x18000462a  mov     [rbp+57h+var_54], 100h
0x180004630  lea     rax, [rbp+57h+var_50]
0x180004634  mov     [rbp+57h+var_90], 0
0x18000463b  lea     r8, [rbp+57h+var_80]; struct BUFFER *
0x18000463f  mov     [rbp+57h+var_60], rax
0x180004643  movups  [rbp+57h+var_50], xmm0
0x180004647  mov     rdi, r9
0x18000464a  mov     rbx, rcx
0x18000464d  movups  [rbp+57h+var_40], xmm0
0x180004651  mov     [rbp+57h+var_88], 0
0x180004659  call    ?GetApplicationSiteName@@YAJPEAVINativeConfigurationSystem@@KPEAVBUFFER@@@Z; GetApplicationSiteName(INativeConfigurationSystem *,ulong,BUFFER *)
0x18000465e  mov     esi, eax
0x180004660  test    eax, eax
0x180004662  jns     short loc_180004675
0x180004664  lea     rcx, [rbp+57h+var_80]
0x180004668  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000466e  mov     eax, esi
0x180004670  jmp     loc_18000477D
0x180004675  mov     rax, [rbx]
0x180004678  lea     rdx, [rbp+57h+var_88]
0x18000467c  mov     rcx, rbx
0x18000467f  mov     rax, [rax+38h]
0x180004683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004688  mov     ebx, eax
0x18000468a  test    eax, eax
0x18000468c  js      loc_180004754
0x180004692  mov     eax, [rdi+28h]
0x180004695  lea     rdx, [rbp+57h+var_90]
0x180004699  mov     rcx, [rbp+57h+var_88]
0x18000469d  mov     r8, r14
0x1800046a0  mov     r9, [rdi+20h]
0x1800046a4  shr     eax, 1
0x1800046a6  mov     [rbp+57h+var_90], eax
0x1800046a9  mov     rax, [rcx]
0x1800046ac  mov     [rsp+0E0h+var_A8], 0
0x1800046b5  mov     [rsp+0E0h+var_B0], 0
0x1800046be  mov     [rsp+0E0h+var_B8], 0
0x1800046c7  mov     rax, [rax+28h]
0x1800046cb  mov     [rsp+0E0h+var_C0], rdx
0x1800046d0  mov     rdx, [rbp+57h+var_60]
0x1800046d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d9  mov     ebx, eax
0x1800046db  cmp     eax, 8007007Ah
0x1800046e0  jnz     short loc_180004754
0x1800046e2  mov     edx, [rbp+57h+var_90]
0x1800046e5  mov     rcx, rdi
0x1800046e8  add     edx, edx
0x1800046ea  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800046f0  test    al, al
0x1800046f2  jnz     short loc_18000470B
0x1800046f4  call    cs:__imp_GetLastError
0x1800046fa  mov     ebx, eax
0x1800046fc  test    eax, eax
0x1800046fe  jle     short loc_180004754
0x180004700  movzx   ebx, ax
0x180004703  or      ebx, 80070000h
0x180004709  jmp     short loc_180004754
0x18000470b  mov     eax, [rdi+28h]
0x18000470e  lea     rdx, [rbp+57h+var_90]
0x180004712  mov     rcx, [rbp+57h+var_88]
0x180004716  mov     r8, r14
0x180004719  mov     r9, [rdi+20h]
0x18000471d  shr     eax, 1
0x18000471f  mov     [rbp+57h+var_90], eax
0x180004722  mov     rax, [rcx]
0x180004725  mov     [rsp+0E0h+var_A8], 0
0x18000472e  mov     [rsp+0E0h+var_B0], 0
0x180004737  mov     [rsp+0E0h+var_B8], 0
0x180004740  mov     rax, [rax+28h]
0x180004744  mov     [rsp+0E0h+var_C0], rdx
0x180004749  mov     rdx, [rbp+57h+var_60]
0x18000474d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004752  mov     ebx, eax
0x180004754  mov     rcx, [rbp+57h+var_88]
0x180004758  test    rcx, rcx
0x18000475b  jz      short loc_180004771
0x18000475d  mov     rax, [rcx]
0x180004760  mov     rax, [rax+10h]
0x180004764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004769  mov     [rbp+57h+var_88], 0
0x180004771  lea     rcx, [rbp+57h+var_80]
0x180004775  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000477b  mov     eax, ebx
0x18000477d  mov     rcx, [rbp+57h+var_30]
0x180004781  xor     rcx, rsp; StackCookie
0x180004784  call    __security_check_cookie
0x180004789  add     rsp, 0C0h
0x180004790  pop     r14
0x180004792  pop     rdi
0x180004793  pop     rsi
0x180004794  pop     rbx
0x180004795  pop     rbp
0x180004796  retn
```
