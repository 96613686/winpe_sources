# CAdapter::RefreshAdapterTable(void)

- ea: `0x18001ac14`
- end: `0x18001ade3`
- name: `?RefreshAdapterTable@CAdapter@@AEAAJXZ`
- size: `463`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001a480`

## callees

- `0x18001ac14`
- `0x1800836c4`
- `0x18008376c`
- `0x180084e28`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001ad04`
- `KERNEL32!GetProcessHeap` at `0x18001ad04`
- `KERNEL32!HeapFree` at `0x18001ad12`
- `KERNEL32!HeapFree` at `0x18001ad12`
- `ole32!CoTaskMemRealloc` at `0x18001ac5f`
- `ole32!CoTaskMemRealloc` at `0x18001ac5f`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001ac4b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001ac9a`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001ac4b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18001ac9a`

## pseudocode

```c
__int64 __fastcall CAdapter::RefreshAdapterTable(void **this)
{
  struct _IP_ADAPTER_ADDRESSES_LH *v2; // rbp
  int AdaptersAddresses; // edi
  bool v4; // sf
  __int64 i; // r14
  struct _IP_ADAPTER_ADDRESSES_LH *j; // rdx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // edx
  OLECHAR *v12; // rcx
  SIZE_T cb; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct _IP_ADAPTER_ADDRESSES_LH *)this[3];
  LODWORD(cb) = *((_DWORD *)this + 5);
  AdaptersAddresses = GetAdaptersAddresses(0, 0, 0, v2, (PULONG)&cb);
  if ( AdaptersAddresses == 111 )
  {
    v2 = (struct _IP_ADAPTER_ADDRESSES_LH *)CoTaskMemRealloc(v2, (unsigned int)cb);
    if ( !v2 && (_DWORD)cb )
    {
      AdaptersAddresses = -2147024882;
LABEL_31:
      *((_DWORD *)this + 2) = 0;
      return (unsigned int)AdaptersAddresses;
    }
    *((_DWORD *)this + 5) = cb;
    this[3] = v2;
    AdaptersAddresses = GetAdaptersAddresses(0, 0, 0, v2, (PULONG)&cb);
  }
  v4 = AdaptersAddresses < 0;
  if ( AdaptersAddresses )
  {
    if ( AdaptersAddresses > 0 )
    {
      AdaptersAddresses = (unsigned __int16)AdaptersAddresses | 0x80070000;
LABEL_29:
      v4 = AdaptersAddresses < 0;
    }
    if ( v4 )
      goto LABEL_31;
  }
  else
  {
    AdaptersAddresses = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
    {
      for ( j = v2; j; j = j->Next )
      {
        if ( j->IfType != 24
          && j->TunnelType == TUNNEL_TYPE_NONE
          && *(_DWORD *)(*((_QWORD *)*this + i) + 8LL) == j->IfIndex )
        {
          j->IfIndex = -1;
          goto LABEL_20;
        }
      }
      v7 = (void *)*((_QWORD *)*this + i);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
      v9 = *((_DWORD *)this + 2);
      v10 = (unsigned int)(i + 1);
      if ( v9 > (unsigned int)v10 )
        memmove_0((char *)*this + 8 * i, (char *)*this + 8 * v10, 8LL * (v9 - (unsigned int)i - 1));
      *((_QWORD *)*this + (unsigned int)--*((_DWORD *)this + 2)) = 0;
      LODWORD(i) = i - 1;
LABEL_20:
      ;
    }
    if ( v2 )
    {
      while ( 1 )
      {
        if ( v2->IfType != 24 && v2->TunnelType == TUNNEL_TYPE_NONE && v2->IfIndex != -1 )
        {
          v11 = *((_DWORD *)this + 2);
          if ( v11 < 0x200 )
          {
            AdaptersAddresses = ChangeArraySize(this, 8 * v11 + 8);
            if ( AdaptersAddresses < 0 )
              goto LABEL_31;
            v12 = (OLECHAR *)*((unsigned int *)this + 2);
            *((_DWORD *)this + 2) = (_DWORD)v12 + 1;
            AdaptersAddresses = CAdapter::InitializeAdapter(v12, (struct _MIB_IF_ROW2 **)*this + (_QWORD)v12, v2);
            if ( AdaptersAddresses < 0 )
              goto LABEL_31;
          }
        }
        v2 = v2->Next;
        if ( !v2 )
          goto LABEL_29;
      }
    }
  }
  return (unsigned int)AdaptersAddresses;
}

```

## disassembly

```asm
0x18001ac14  mov     r11, rsp
0x18001ac17  mov     [r11+10h], rbx
0x18001ac1b  mov     [r11+18h], rbp
0x18001ac1f  push    rsi
0x18001ac20  push    rdi
0x18001ac21  push    r13
0x18001ac23  push    r14
0x18001ac25  push    r15
0x18001ac27  sub     rsp, 30h
0x18001ac2b  mov     eax, [rcx+14h]
0x18001ac2e  mov     rsi, rcx
0x18001ac31  mov     rbp, [rcx+18h]
0x18001ac35  xor     r8d, r8d; Reserved
0x18001ac38  mov     dword ptr [rsp+58h+cb], eax
0x18001ac3c  mov     r9, rbp; AdapterAddresses
0x18001ac3f  lea     rax, [r11+8]
0x18001ac43  xor     edx, edx; Flags
0x18001ac45  xor     ecx, ecx; Family
0x18001ac47  mov     [r11-38h], rax
0x18001ac4b  call    cs:__imp_GetAdaptersAddresses
0x18001ac51  mov     edi, eax
0x18001ac53  cmp     eax, 6Fh ; 'o'
0x18001ac56  jnz     short loc_18001ACA2
0x18001ac58  mov     edx, dword ptr [rsp+58h+cb]; cb
0x18001ac5c  mov     rcx, rbp; pv
0x18001ac5f  call    cs:__imp_CoTaskMemRealloc
0x18001ac65  mov     rbp, rax
0x18001ac68  mov     eax, dword ptr [rsp+58h+cb]
0x18001ac6c  test    rbp, rbp
0x18001ac6f  jnz     short loc_18001AC7F
0x18001ac71  test    eax, eax
0x18001ac73  jz      short loc_18001AC7F
0x18001ac75  mov     edi, 8007000Eh
0x18001ac7a  jmp     loc_18001ADC3
0x18001ac7f  mov     [rsi+14h], eax
0x18001ac82  mov     r9, rbp; AdapterAddresses
0x18001ac85  lea     rax, [rsp+58h+cb]
0x18001ac8a  mov     [rsi+18h], rbp
0x18001ac8e  xor     r8d, r8d; Reserved
0x18001ac91  mov     [rsp+58h+SizePointer], rax; SizePointer
0x18001ac96  xor     edx, edx; Flags
0x18001ac98  xor     ecx, ecx; Family
0x18001ac9a  call    cs:__imp_GetAdaptersAddresses
0x18001aca0  mov     edi, eax
0x18001aca2  test    edi, edi
0x18001aca4  jz      short loc_18001ACBA
0x18001aca6  jle     loc_18001ADC1
0x18001acac  movzx   edi, di
0x18001acaf  or      edi, 80070000h
0x18001acb5  jmp     loc_18001ADBF
0x18001acba  xor     edi, edi
0x18001acbc  xor     r14d, r14d
0x18001acbf  or      r13d, 0FFFFFFFFh
0x18001acc3  cmp     [rsi+8], edi
0x18001acc6  jbe     loc_18001AD5E
0x18001accc  mov     rdx, rbp
0x18001accf  test    rdx, rdx
0x18001acd2  jz      short loc_18001ACFD
0x18001acd4  cmp     dword ptr [rdx+64h], 18h
0x18001acd8  jz      short loc_18001ACF1
0x18001acda  cmp     [rdx+110h], edi
0x18001ace0  jnz     short loc_18001ACF1
0x18001ace2  mov     rax, [rsi]
0x18001ace5  mov     rcx, [rax+r14*8]
0x18001ace9  mov     eax, [rdx+4]
0x18001acec  cmp     [rcx+8], eax
0x18001acef  jz      short loc_18001ACF7
0x18001acf1  mov     rdx, [rdx+8]
0x18001acf5  jmp     short loc_18001ACCF
0x18001acf7  mov     [rdx+4], r13d
0x18001acfb  jmp     short loc_18001AD51
0x18001acfd  mov     rax, [rsi]
0x18001ad00  mov     rbx, [rax+r14*8]
0x18001ad04  call    cs:__imp_GetProcessHeap
0x18001ad0a  mov     r8, rbx; lpMem
0x18001ad0d  xor     edx, edx; dwFlags
0x18001ad0f  mov     rcx, rax; hHeap
0x18001ad12  call    cs:__imp_HeapFree
0x18001ad18  mov     eax, [rsi+8]
0x18001ad1b  lea     edx, [r14+1]
0x18001ad1f  cmp     eax, edx
0x18001ad21  jbe     short loc_18001AD3E
0x18001ad23  mov     rcx, [rsi]
0x18001ad26  sub     eax, r14d
0x18001ad29  lea     r8d, [rax-1]
0x18001ad2d  lea     rdx, [rcx+rdx*8]; Src
0x18001ad31  shl     r8, 3; Size
0x18001ad35  lea     rcx, [rcx+r14*8]; void *
0x18001ad39  call    memmove_0
0x18001ad3e  mov     ecx, [rsi+8]
0x18001ad41  mov     rax, [rsi]
0x18001ad44  dec     ecx
0x18001ad46  mov     [rax+rcx*8], rdi
0x18001ad4a  add     [rsi+8], r13d
0x18001ad4e  add     r14d, r13d
0x18001ad51  inc     r14d
0x18001ad54  cmp     r14d, [rsi+8]
0x18001ad58  jb      loc_18001ACCC
0x18001ad5e  test    rbp, rbp
0x18001ad61  jz      short loc_18001ADCA
0x18001ad63  cmp     dword ptr [rbp+64h], 18h
0x18001ad67  jz      short loc_18001ADB6
0x18001ad69  cmp     dword ptr [rbp+110h], 0
0x18001ad70  jnz     short loc_18001ADB6
0x18001ad72  cmp     [rbp+4], r13d
0x18001ad76  jz      short loc_18001ADB6
0x18001ad78  mov     edx, [rsi+8]
0x18001ad7b  cmp     edx, 200h
0x18001ad81  jnb     short loc_18001ADB6
0x18001ad83  lea     edx, ds:8[rdx*8]; unsigned int
0x18001ad8a  mov     rcx, rsi; void **
0x18001ad8d  call    ?ChangeArraySize@@YAJPEAPEAXK@Z; ChangeArraySize(void * *,ulong)
0x18001ad92  mov     edi, eax
0x18001ad94  test    eax, eax
0x18001ad96  js      short loc_18001ADC3
0x18001ad98  mov     ecx, [rsi+8]; this
0x18001ad9b  mov     r8, rbp; struct _IP_ADAPTER_ADDRESSES_LH *
0x18001ad9e  lea     eax, [rcx+1]
0x18001ada1  mov     [rsi+8], eax
0x18001ada4  mov     rax, [rsi]
0x18001ada7  lea     rdx, [rax+rcx*8]; struct tagADAPTER_INFOEX **
0x18001adab  call    ?InitializeAdapter@CAdapter@@AEAAJPEAPEAUtagADAPTER_INFOEX@@PEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; CAdapter::InitializeAdapter(tagADAPTER_INFOEX * *,_IP_ADAPTER_ADDRESSES_LH *)
0x18001adb0  mov     edi, eax
0x18001adb2  test    eax, eax
0x18001adb4  js      short loc_18001ADC3
0x18001adb6  mov     rbp, [rbp+8]
0x18001adba  test    rbp, rbp
0x18001adbd  jnz     short loc_18001AD63
0x18001adbf  test    edi, edi
0x18001adc1  jns     short loc_18001ADCA
0x18001adc3  mov     dword ptr [rsi+8], 0
0x18001adca  mov     rbx, [rsp+58h+arg_8]
0x18001adcf  mov     eax, edi
0x18001add1  mov     rbp, [rsp+58h+arg_10]
0x18001add6  add     rsp, 30h
0x18001adda  pop     r15
0x18001addc  pop     r14
0x18001adde  pop     r13
0x18001ade0  pop     rdi
0x18001ade1  pop     rsi
0x18001ade2  retn
```
