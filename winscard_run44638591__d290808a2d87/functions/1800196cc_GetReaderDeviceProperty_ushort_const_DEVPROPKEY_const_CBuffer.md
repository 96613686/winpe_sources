# GetReaderDeviceProperty(ushort const *,_DEVPROPKEY const *,CBuffer &)

- ea: `0x1800196cc`
- end: `0x1800198b5`
- name: `?GetReaderDeviceProperty@@YAJPEBGPEBU_DEVPROPKEY@@AEAVCBuffer@@@Z`
- size: `489`
- prototype: `int(const unsigned __int16 *, const struct _DEVPROPKEY *, struct CBuffer *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a30`

## callees

- `0x180003ee0`
- `0x180014b00`
- `0x1800196cc`
- `0x18001be10`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001973d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001973d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019857`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180019729`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180019729`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019889`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019889`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180019776`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180019776`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800197d2`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001984d`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800197d2`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001984d`

## pseudocode

```c
__int64 __fastcall GetReaderDeviceProperty(
        const unsigned __int16 *a1,
        const struct _DEVPROPKEY *a2,
        struct CBuffer *a3)
{
  ulong v5; // esi
  __int64 DeviceInfoList; // rdi
  DWORD v7; // eax
  unsigned int v8; // ebx
  unsigned __int8 *v9; // rax
  int v10; // edx
  __int64 result; // rax
  unsigned int v12; // [rsp+40h] [rbp-88h] BYREF
  ulong v13; // [rsp+44h] [rbp-84h]
  int v14; // [rsp+48h] [rbp-80h] BYREF
  ulong pExceptionObject; // [rsp+4Ch] [rbp-7Ch] BYREF
  ulong LastError; // [rsp+50h] [rbp-78h] BYREF
  ulong v17; // [rsp+54h] [rbp-74h] BYREF
  ulong v18; // [rsp+58h] [rbp-70h] BYREF
  __int64 v19; // [rsp+60h] [rbp-68h]
  ulong v20; // [rsp+68h] [rbp-60h] BYREF
  _DWORD v21[12]; // [rsp+70h] [rbp-58h] BYREF

  v5 = 0;
  v19 = -1;
  memset(v21, 0, sizeof(v21));
  v14 = 0;
  v12 = 0;
  try
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v19 = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    v21[0] = 48;
    if ( !(unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, v21) )
    {
      LastError = GetLastError();
      throw &LastError;
    }
    if ( !(unsigned int)DevObjGetDeviceProperty(DeviceInfoList, v21, &DEVPKEY_DrvPkg_Icon, &v14, 0, 0, &v12, 0) )
    {
      v7 = GetLastError();
      if ( v7 != 122 )
      {
        v17 = v7;
        throw &v17;
      }
    }
    v8 = v12;
    CBuffer::Presize(a3, v12, 0);
    *((_DWORD *)a3 + 4) = v8;
    v9 = CBuffer::Access(a3, 0);
    if ( !(unsigned int)DevObjGetDeviceProperty(
                          DeviceInfoList,
                          v21,
                          &DEVPKEY_DrvPkg_Icon,
                          &v14,
                          v9,
                          *((_DWORD *)a3 + 5),
                          &v12,
                          v10) )
    {
      v18 = GetLastError();
      throw &v18;
    }
  }
  catch ( ulong v20 )
  {
    v13 = v20;
    goto LABEL_11;
  }
  catch ( ... )
  {
    v13 = -2146435068;
LABEL_11:
    DeviceInfoList = v19;
    v5 = v13;
    if ( v19 != -1 )
      goto LABEL_12;
LABEL_13:
    result = v5;
  }
LABEL_12:
  DevObjDestroyDeviceInfoList(DeviceInfoList);
  goto LABEL_13;
}

```

## disassembly

```asm
0x1800196cc  mov     r11, rsp
0x1800196cf  mov     [r11+10h], rbx
0x1800196d3  push    rsi
0x1800196d4  push    rdi
0x1800196d5  push    r14
0x1800196d7  sub     rsp, 0B0h
0x1800196de  mov     rax, cs:__security_cookie
0x1800196e5  xor     rax, rsp
0x1800196e8  mov     [rsp+0C8h+var_28], rax
0x1800196f0  mov     r14, r8
0x1800196f3  mov     rbx, rcx
0x1800196f6  xor     esi, esi
0x1800196f8  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFFh
0x180019700  xorps   xmm0, xmm0
0x180019703  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x180019708  movups  xmmword ptr [r11-48h], xmm0
0x18001970d  movups  xmmword ptr [r11-38h], xmm0
0x180019712  mov     [rsp+0C8h+var_80], esi
0x180019716  mov     [rsp+0C8h+var_88], esi
0x18001971a  mov     [rsp+0C8h+var_A8], rsi
0x18001971f  xor     r9d, r9d
0x180019722  xor     r8d, r8d
0x180019725  xor     edx, edx
0x180019727  xor     ecx, ecx
0x180019729  call    cs:__imp_DevObjCreateDeviceInfoList
0x18001972f  mov     rdi, rax
0x180019732  mov     [rsp+0C8h+var_68], rax
0x180019737  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001973b  jnz     short loc_180019758
0x18001973d  call    cs:__imp_GetLastError
0x180019743  mov     [rsp+0C8h+pExceptionObject], eax
0x180019747  lea     rdx, _TI1K; pThrowInfo
0x18001974e  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180019753  call    _CxxThrowException_0
0x180019758  mov     [rsp+0C8h+var_58], 30h ; '0'
0x180019760  lea     rax, [rsp+0C8h+var_58]
0x180019765  mov     [rsp+0C8h+var_A8], rax
0x18001976a  xor     r9d, r9d
0x18001976d  xor     r8d, r8d
0x180019770  mov     rdx, rbx
0x180019773  mov     rcx, rdi
0x180019776  call    cs:__imp_DevObjOpenDeviceInfo
0x18001977c  test    eax, eax
0x18001977e  jnz     short loc_18001979B
0x180019780  call    cs:__imp_GetLastError
0x180019786  mov     [rsp+0C8h+var_78], eax
0x18001978a  lea     rdx, _TI1K; pThrowInfo
0x180019791  lea     rcx, [rsp+0C8h+var_78]; pExceptionObject
0x180019796  call    _CxxThrowException_0
0x18001979b  mov     [rsp+0C8h+var_90], 0
0x1800197a3  lea     rax, [rsp+0C8h+var_88]
0x1800197a8  mov     [rsp+0C8h+var_98], rax
0x1800197ad  mov     [rsp+0C8h+var_A0], 0
0x1800197b5  mov     [rsp+0C8h+var_A8], 0
0x1800197be  lea     r9, [rsp+0C8h+var_80]
0x1800197c3  lea     r8, DEVPKEY_DrvPkg_Icon
0x1800197ca  lea     rdx, [rsp+0C8h+var_58]
0x1800197cf  mov     rcx, rdi
0x1800197d2  call    cs:__imp_DevObjGetDeviceProperty
0x1800197d8  test    eax, eax
0x1800197da  jnz     short loc_1800197FC
0x1800197dc  call    cs:__imp_GetLastError
0x1800197e2  cmp     eax, 7Ah ; 'z'
0x1800197e5  jz      short loc_1800197FC
0x1800197e7  mov     [rsp+0C8h+var_74], eax
0x1800197eb  lea     rdx, _TI1K; pThrowInfo
0x1800197f2  lea     rcx, [rsp+0C8h+var_74]; pExceptionObject
0x1800197f7  call    _CxxThrowException_0
0x1800197fc  mov     ebx, [rsp+0C8h+var_88]
0x180019800  xor     r8d, r8d; int
0x180019803  mov     edx, ebx; unsigned int
0x180019805  mov     rcx, r14; this
0x180019808  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18001980d  mov     [r14+10h], ebx
0x180019811  xor     edx, edx; unsigned int
0x180019813  mov     rcx, r14; this
0x180019816  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x18001981b  mov     rcx, rax
0x18001981e  mov     [rsp+0C8h+var_90], edx
0x180019822  lea     rax, [rsp+0C8h+var_88]
0x180019827  mov     [rsp+0C8h+var_98], rax
0x18001982c  mov     eax, [r14+14h]
0x180019830  mov     [rsp+0C8h+var_A0], eax
0x180019834  mov     [rsp+0C8h+var_A8], rcx
0x180019839  lea     r9, [rsp+0C8h+var_80]
0x18001983e  lea     r8, DEVPKEY_DrvPkg_Icon
0x180019845  lea     rdx, [rsp+0C8h+var_58]
0x18001984a  mov     rcx, rdi
0x18001984d  call    cs:__imp_DevObjGetDeviceProperty
0x180019853  test    eax, eax
0x180019855  jnz     short loc_180019873
0x180019857  call    cs:__imp_GetLastError
0x18001985d  mov     [rsp+0C8h+var_70], eax
0x180019861  lea     rdx, _TI1K; pThrowInfo
0x180019868  lea     rcx, [rsp+0C8h+var_70]; pExceptionObject
0x18001986d  call    _CxxThrowException_0
0x180019873  jmp     short loc_180019886
0x180019875  jmp     short $+2
0x180019877  mov     rdi, [rsp+0C8h+var_68]
0x18001987c  mov     esi, [rsp+0C8h+var_84]
0x180019880  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180019884  jz      short loc_18001988F
0x180019886  mov     rcx, rdi
0x180019889  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001988f  mov     eax, esi
0x180019891  mov     rcx, [rsp+0C8h+var_28]
0x180019899  xor     rcx, rsp; StackCookie
0x18001989c  call    __security_check_cookie
0x1800198a1  mov     rbx, [rsp+0C8h+arg_8]
0x1800198a9  add     rsp, 0B0h
0x1800198b0  pop     r14
0x1800198b2  pop     rdi
0x1800198b3  pop     rsi
0x1800198b4  retn
```
