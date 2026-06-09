# CSrDrvWuHelper::_GetWindirPathFromGroup(_SPP_GROUP_PROP const *,CBsString *)

- ea: `0x18000ca98`
- end: `0x18000cc1a`
- name: `?_GetWindirPathFromGroup@CSrDrvWuHelper@@CAJPEBU_SPP_GROUP_PROP@@PEAVCBsString@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(const struct _SPP_GROUP_PROP *, struct CBsString *, __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b3b0`

## callees

- `0x180003ce0`
- `0x18000c258`
- `0x18000c890`
- `0x18000ca98`
- `0x18000d348`
- `0x18000d43c`
- `0x180015760`
- `0x1800157be`
- `0x1800157f0`

## string_xrefs

- `0x18000caf7`: `CSrDrvWuHelper::_GetWindirPathFromGroup`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_GetWindirPathFromGroup(
        const struct _SPP_GROUP_PROP *a1,
        struct CBsString *a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int64 v6; // rbx
  unsigned __int16 v7; // r9
  _BYTE *v8; // rax
  __int16 v9; // ax
  int BootVolumeProp; // ebx
  bool v11; // zf
  _WORD *v12; // rdx
  __int64 v13; // r8
  unsigned __int16 v14; // r9
  int v16; // [rsp+20h] [rbp-69h] BYREF
  int v17; // [rsp+28h] [rbp-61h] BYREF
  __int16 v18; // [rsp+2Ch] [rbp-5Dh]
  __int16 v19; // [rsp+2Eh] [rbp-5Bh]
  _QWORD v20[2]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v21[80]; // [rsp+70h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSrDrvWuHelper::_GetWindirPathFromGroup", 0x39Bu, a4);
  v6 = 80;
  memset_0(v21, 0, sizeof(v21));
  v20[1] = 0;
  v20[0] = qword_18001A620;
  v8 = v21;
  v16 = 0;
  do
  {
    *v8++ = 0;
    --v6;
  }
  while ( v6 );
  v9 = 929;
  if ( a1 && (v18 = 929, v9 = 930, a2) )
  {
    v11 = *((_DWORD *)a2 + 2) == 0;
    v17 = 0;
    v18 = 930;
    if ( !v11 )
    {
      v12 = *(_WORD **)a2;
      *((_DWORD *)a2 + 2) = 0;
      *v12 = 0;
    }
    BootVolumeProp = CSrDrvWuHelper::_GetBootVolumeProp(a1, (struct _SPP_BOOT_VOLUME_PROP *)v21, &v16, v7);
    v17 = BootVolumeProp;
    v9 = 934;
    if ( BootVolumeProp >= 0 )
    {
      v18 = 934;
      if ( !v16 )
      {
        v17 = 0;
        v9 = 938;
        BootVolumeProp = 0;
LABEL_16:
        v18 = v9;
        goto LABEL_17;
      }
      BootVolumeProp = CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(
                         (const struct _SPP_BOOT_VOLUME_PROP *)v21,
                         a2,
                         v13,
                         v14);
      v17 = BootVolumeProp;
      v9 = 941;
      if ( BootVolumeProp >= 0 )
        goto LABEL_16;
    }
  }
  else
  {
    BootVolumeProp = -2147024809;
    v17 = -2147024809;
  }
  v19 = v9;
LABEL_17:
  CBsString::_Release((CBsString *)v20);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)BootVolumeProp;
}

```

## disassembly

```asm
0x18000ca98  mov     [rsp-8+arg_10], rbx
0x18000ca9d  push    rbp
0x18000ca9e  push    rsi
0x18000ca9f  push    rdi
0x18000caa0  lea     rbp, [rsp-47h]
0x18000caa5  sub     rsp, 0D0h
0x18000caac  mov     rax, cs:__security_cookie
0x18000cab3  xor     rax, rsp
0x18000cab6  mov     [rbp+57h+var_20], rax
0x18000caba  mov     rdi, rdx
0x18000cabd  mov     rsi, rcx
0x18000cac0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cac7  lea     rax, WPP_GLOBAL_Control
0x18000cace  cmp     rcx, rax
0x18000cad1  jz      short loc_18000CAF1
0x18000cad3  test    dword ptr [rcx+1Ch], 20000000h
0x18000cada  jz      short loc_18000CAF1
0x18000cadc  mov     rcx, [rcx+10h]
0x18000cae0  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000cae7  mov     edx, 25h ; '%'
0x18000caec  call    WPP_SF_
0x18000caf1  mov     r8d, 39Bh; unsigned __int16
0x18000caf7  lea     rdx, aCsrdrvwuhelper_0; "CSrDrvWuHelper::_GetWindirPathFromGroup"
0x18000cafe  lea     rcx, [rbp+57h+var_B8]; this
0x18000cb02  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000cb07  mov     ebx, 50h ; 'P'
0x18000cb0c  lea     rcx, [rbp+57h+var_70]; void *
0x18000cb10  mov     r8d, ebx; Size
0x18000cb13  xor     edx, edx; Val
0x18000cb15  call    memset_0
0x18000cb1a  lea     rax, qword_18001A620
0x18000cb21  mov     [rbp+57h+var_78], 0
0x18000cb29  mov     [rbp+57h+var_80], rax
0x18000cb2d  lea     rax, [rbp+57h+var_70]
0x18000cb31  mov     [rbp+57h+var_C0], 0
0x18000cb38  mov     byte ptr [rax], 0
0x18000cb3b  inc     rax
0x18000cb3e  sub     rbx, 1
0x18000cb42  jnz     short loc_18000CB38
0x18000cb44  mov     eax, 3A1h
0x18000cb49  test    rsi, rsi
0x18000cb4c  jnz     short loc_18000CB5F
0x18000cb4e  mov     ebx, 80070057h
0x18000cb53  mov     [rbp+57h+var_B8], ebx
0x18000cb56  mov     [rbp+57h+var_B2], ax
0x18000cb5a  jmp     loc_18000CBE7
0x18000cb5f  mov     [rbp+57h+var_B4], ax
0x18000cb63  mov     eax, 3A2h
0x18000cb68  test    rdi, rdi
0x18000cb6b  jz      short loc_18000CB4E
0x18000cb6d  cmp     dword ptr [rdi+8], 0
0x18000cb71  mov     [rbp+57h+var_B8], 0
0x18000cb78  mov     [rbp+57h+var_B4], ax
0x18000cb7c  jz      short loc_18000CB8D
0x18000cb7e  mov     rdx, [rdi]
0x18000cb81  xor     eax, eax
0x18000cb83  mov     dword ptr [rdi+8], 0
0x18000cb8a  mov     [rdx], ax
0x18000cb8d  lea     r8, [rbp+57h+var_C0]; int *
0x18000cb91  mov     rcx, rsi; struct _SPP_GROUP_PROP *
0x18000cb94  lea     rdx, [rbp+57h+var_70]; struct _SPP_BOOT_VOLUME_PROP *
0x18000cb98  call    ?_GetBootVolumeProp@CSrDrvWuHelper@@CAJPEBU_SPP_GROUP_PROP@@PEAU_SPP_BOOT_VOLUME_PROP@@PEAH@Z; CSrDrvWuHelper::_GetBootVolumeProp(_SPP_GROUP_PROP const *,_SPP_BOOT_VOLUME_PROP *,int *)
0x18000cb9d  mov     ebx, eax
0x18000cb9f  mov     [rbp+57h+var_B8], eax
0x18000cba2  test    eax, eax
0x18000cba4  mov     eax, 3A6h
0x18000cba9  js      short loc_18000CB56
0x18000cbab  cmp     [rbp+57h+var_C0], 0
0x18000cbaf  mov     [rbp+57h+var_B4], ax
0x18000cbb3  jnz     short loc_18000CBC5
0x18000cbb5  mov     [rbp+57h+var_B8], 0
0x18000cbbc  mov     eax, 3AAh
0x18000cbc1  xor     ebx, ebx
0x18000cbc3  jmp     short loc_18000CBE3
0x18000cbc5  mov     rdx, rdi; struct CBsString *
0x18000cbc8  lea     rcx, [rbp+57h+var_70]; struct _SPP_BOOT_VOLUME_PROP *
0x18000cbcc  call    ?_GetWindirPathFromBootVolumeProp@CSrDrvWuHelper@@CAJPEBU_SPP_BOOT_VOLUME_PROP@@PEAVCBsString@@@Z; CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(_SPP_BOOT_VOLUME_PROP const *,CBsString *)
0x18000cbd1  mov     ebx, eax
0x18000cbd3  mov     [rbp+57h+var_B8], eax
0x18000cbd6  test    eax, eax
0x18000cbd8  mov     eax, 3ADh
0x18000cbdd  js      loc_18000CB56
0x18000cbe3  mov     [rbp+57h+var_B4], ax
0x18000cbe7  lea     rcx, [rbp+57h+var_80]; this
0x18000cbeb  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000cbf0  lea     rcx, [rbp+57h+var_B8]; this
0x18000cbf4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000cbf9  mov     eax, ebx
0x18000cbfb  mov     rcx, [rbp+57h+var_20]
0x18000cbff  xor     rcx, rsp; StackCookie
0x18000cc02  call    __security_check_cookie
0x18000cc07  mov     rbx, [rsp+0E0h+arg_10]
0x18000cc0f  add     rsp, 0D0h
0x18000cc16  pop     rdi
0x18000cc17  pop     rsi
0x18000cc18  pop     rbp
0x18000cc19  retn
```
