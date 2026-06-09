# CUsbDevice::PopulateDeviceDescriptor(void)

- ea: `0x180009b24`
- end: `0x180009c49`
- name: `?PopulateDeviceDescriptor@CUsbDevice@@AEAAXXZ`
- size: `293`
- prototype: `void __fastcall(CUsbDevice *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800097ec`

## callees

- `0x180002e6e`
- `0x180004060`
- `0x1800040cc`
- `0x1800080c8`
- `0x180009520`
- `0x180009630`
- `0x180009b24`

## pseudocode

```c
void __fastcall CUsbDevice::PopulateDeviceDescriptor(CUsbDevice *this)
{
  char *v2; // rsi
  USB_PIPE_INFO *PipeList; // rax
  size_t v4; // rbx
  struct _USB_NODE_CONNECTION_INFORMATION_EX *v5; // rbx
  char *v6; // rsi
  USHORT *p_bcdDevice; // rax
  size_t v8; // rbx
  struct _USB_NODE_CONNECTION_INFORMATION_EX *v9; // rbx
  struct _USB_NODE_CONNECTION_INFORMATION_EX *v10; // [rsp+20h] [rbp-28h] BYREF
  void *v11; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+30h] [rbp-18h]

  std::vector<_bstr_t>::vector<_bstr_t>(&v10);
  v2 = (char *)v11;
  if ( (unsigned __int64)((_BYTE *)v11 - (_BYTE *)v10) <= 0x23 )
  {
    if ( (unsigned __int64)((_BYTE *)v11 - (_BYTE *)v10) >= 0x23 )
      goto LABEL_8;
    if ( (unsigned __int64)(v12 - (_QWORD)v10) < 0x23 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v10, 35);
      goto LABEL_8;
    }
    v4 = 35 - ((_BYTE *)v11 - (_BYTE *)v10);
    memset_0(v11, 0, v4);
    PipeList = (USB_PIPE_INFO *)&v2[v4];
  }
  else
  {
    PipeList = v10->PipeList;
  }
  v11 = PipeList;
LABEL_8:
  v5 = v10;
  CUsbDevice::GetNodeConnectionInformation(*((CUsbDevice **)this + 1), *((_DWORD *)this + 18), v10);
  *(USB_DEVICE_DESCRIPTOR *)((char *)this + 40) = v5->DeviceDescriptor;
  *((_DWORD *)this + 9) = v5->Speed;
  v6 = (char *)v11;
  if ( (unsigned __int64)((_BYTE *)v11 - (_BYTE *)v10) <= 0x10 )
  {
    if ( (unsigned __int64)((_BYTE *)v11 - (_BYTE *)v10) >= 0x10 )
      goto LABEL_15;
    if ( (unsigned __int64)(v12 - (_QWORD)v10) < 0x10 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v10, 16);
      goto LABEL_15;
    }
    v8 = 16 - ((_BYTE *)v11 - (_BYTE *)v10);
    memset_0(v11, 0, v8);
    p_bcdDevice = (USHORT *)&v6[v8];
  }
  else
  {
    p_bcdDevice = &v10->DeviceDescriptor.bcdDevice;
  }
  v11 = p_bcdDevice;
LABEL_15:
  v9 = v10;
  CUsbDevice::GetNodeConnectionInformationV2(
    *((CUsbDevice **)this + 1),
    *((_DWORD *)this + 18),
    (struct _USB_NODE_CONNECTION_INFORMATION_EX_V2 *)v10);
  if ( (v9->DeviceDescriptor.idVendor & 1) != 0 )
    *((_DWORD *)this + 9) = 3;
  if ( v10 )
    std::_Deallocate<16>(v10, v12 - (_QWORD)v10);
}

```

## disassembly

```asm
0x180009b24  push    rbp
0x180009b26  push    rbx
0x180009b27  push    rsi
0x180009b28  push    rdi
0x180009b29  mov     rbp, rsp
0x180009b2c  sub     rsp, 48h
0x180009b30  mov     rdi, rcx
0x180009b33  lea     rcx, [rbp+var_28]
0x180009b37  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x180009b3c  nop
0x180009b3d  mov     rcx, [rbp+var_28]
0x180009b41  mov     rsi, [rbp+var_20]
0x180009b45  mov     rdx, rsi
0x180009b48  sub     rdx, rcx
0x180009b4b  mov     ebx, 23h ; '#'
0x180009b50  cmp     rdx, rbx
0x180009b53  jbe     short loc_180009B5B
0x180009b55  lea     rax, [rcx+23h]
0x180009b59  jmp     short loc_180009B8B
0x180009b5b  jnb     short loc_180009B8F
0x180009b5d  mov     rax, [rbp+var_18]
0x180009b61  sub     rax, rcx
0x180009b64  cmp     rax, rbx
0x180009b67  jnb     short loc_180009B77
0x180009b69  mov     rdx, rbx
0x180009b6c  lea     rcx, [rbp+var_28]
0x180009b70  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180009b75  jmp     short loc_180009B8F
0x180009b77  sub     rbx, rdx
0x180009b7a  mov     r8, rbx; Size
0x180009b7d  xor     edx, edx; Val
0x180009b7f  mov     rcx, rsi; void *
0x180009b82  call    memset_0
0x180009b87  lea     rax, [rbx+rsi]
0x180009b8b  mov     [rbp+var_20], rax
0x180009b8f  mov     rbx, [rbp+var_28]
0x180009b93  mov     r8, rbx; struct _USB_NODE_CONNECTION_INFORMATION_EX *
0x180009b96  mov     edx, [rdi+48h]; unsigned int
0x180009b99  mov     rcx, [rdi+8]; this
0x180009b9d  call    ?GetNodeConnectionInformation@CUsbDevice@@QEAAXKPEAU_USB_NODE_CONNECTION_INFORMATION_EX@@@Z; CUsbDevice::GetNodeConnectionInformation(ulong,_USB_NODE_CONNECTION_INFORMATION_EX *)
0x180009ba2  movups  xmm0, xmmword ptr [rbx+4]
0x180009ba6  movups  xmmword ptr [rdi+28h], xmm0
0x180009baa  movzx   eax, word ptr [rbx+14h]
0x180009bae  mov     [rdi+38h], ax
0x180009bb2  movzx   eax, byte ptr [rbx+17h]
0x180009bb6  mov     [rdi+24h], eax
0x180009bb9  mov     rdx, [rbp+var_28]
0x180009bbd  mov     rsi, [rbp+var_20]
0x180009bc1  mov     rcx, rsi
0x180009bc4  sub     rcx, rdx
0x180009bc7  mov     ebx, 10h
0x180009bcc  cmp     rcx, rbx
0x180009bcf  jbe     short loc_180009BD7
0x180009bd1  lea     rax, [rdx+10h]
0x180009bd5  jmp     short loc_180009C07
0x180009bd7  jnb     short loc_180009C0B
0x180009bd9  mov     rax, [rbp+var_18]
0x180009bdd  sub     rax, rdx
0x180009be0  cmp     rax, rbx
0x180009be3  jnb     short loc_180009BF3
0x180009be5  mov     rdx, rbx
0x180009be8  lea     rcx, [rbp+var_28]
0x180009bec  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180009bf1  jmp     short loc_180009C0B
0x180009bf3  sub     rbx, rcx
0x180009bf6  mov     r8, rbx; Size
0x180009bf9  xor     edx, edx; Val
0x180009bfb  mov     rcx, rsi; void *
0x180009bfe  call    memset_0
0x180009c03  lea     rax, [rbx+rsi]
0x180009c07  mov     [rbp+var_20], rax
0x180009c0b  mov     rbx, [rbp+var_28]
0x180009c0f  mov     r8, rbx; struct _USB_NODE_CONNECTION_INFORMATION_EX_V2 *
0x180009c12  mov     edx, [rdi+48h]; unsigned int
0x180009c15  mov     rcx, [rdi+8]; this
0x180009c19  call    ?GetNodeConnectionInformationV2@CUsbDevice@@QEAAXKPEAU_USB_NODE_CONNECTION_INFORMATION_EX_V2@@@Z; CUsbDevice::GetNodeConnectionInformationV2(ulong,_USB_NODE_CONNECTION_INFORMATION_EX_V2 *)
0x180009c1e  test    byte ptr [rbx+0Ch], 1
0x180009c22  jz      short loc_180009C2B
0x180009c24  mov     dword ptr [rdi+24h], 3
0x180009c2b  mov     rcx, [rbp+var_28]
0x180009c2f  test    rcx, rcx
0x180009c32  jz      short loc_180009C40
0x180009c34  mov     rdx, [rbp+var_18]
0x180009c38  sub     rdx, rcx
0x180009c3b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009c40  add     rsp, 48h
0x180009c44  pop     rdi
0x180009c45  pop     rsi
0x180009c46  pop     rbx
0x180009c47  pop     rbp
0x180009c48  retn
```
